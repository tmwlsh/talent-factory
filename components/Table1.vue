<template>
  <div class="table-outer">
    <div class="table">
      <div class="table-header row">
        <div class="data" @click.prevent="setActiveSort('slug')">
          <span>Country</span>
        </div>
        <div class="data" @click.prevent="setActiveSort('playerCount')">
          <span>Player Count</span>
        </div>
        <div class="data" @click.prevent="setActiveSort('averageNetDifference')">
          <span>Average Net Difference</span>
        </div>
        <div class="data" @click.prevent="setActiveSort('averagePercentageDifference')">
          <span>Average Percentage Difference</span>
        </div>
      </div>
      <div class="row-outer" v-for="row in filteredTableData" :key="row.country">
        <div class="row" @click.prevent="toggleDisplay(row.slug)">
          <div class="data">
            {{row.name}}
          </div>
          <div class="data">
            {{row.playerCount}}
          </div>
          <div class="data">
            {{row.averageNetDifference | numberFilter}}
          </div>
          <div class="data">
            {{row.averagePercentageDifference}}%
          </div>
        </div>
        <transition name="slide-fade">
          <div class="row-inner-container" v-if="activeCountries.indexOf(row.slug) !== -1">
            <div class="row inner" v-for="club in row.data" :key="club.name">
              <div class="data">
                {{club.name}}
              </div>
              <div class="data">
                {{club.playerCount}}
              </div>
              <div class="data">
                {{club.averageNetDifference | numberFilter}}
              </div>
              <div class="data">
                {{club.averagePercentageDifference}}%
              </div>
            </div>
          </div>
        </transition>
      </div>
    </div>
    <button class="show-more" v-show="!maxItemsShown" @click="increaseItems()">Show More</button>
  </div>
</template>

<script>
  export default {
    props: ['tableData'],
    data: () => {
      return {
        activeCountries: [],
        activeSort: false,
        sortAscending: true,
        numberOfItems: 20,
        maxItemsShown: false,
      }
    },
    methods: {
      increaseItems() {
        this.numberOfItems = this.numberOfItems + 20;
        if(this.numberOfItems >= this.preSortedData.length) {
          this.numberOfItems = this.preSortedData.length;
          this.maxItemsShown = true;
        }
      },
      setActiveSort(id) {
        if(id === this.activeSort) this.sortAscending = !this.sortAscending
        else this.sortAscending
        this.activeSort = id
      },
      toggleDisplay(slug) {
        if(this.activeCountries.indexOf(slug) === -1) {
            this.activeCountries.push(slug);
        }
        else {
          this.activeCountries.splice(this.activeCountries.indexOf(slug), 1)
        }
      },
    },
    filters: {
      numberFilter(num) {
        const euros = (num * 1.01).toFixed(2);
        return `€${euros.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",")}`;
      }
    },
    computed: {
      filteredTableData: function () {
        const clonedData = JSON.parse(JSON.stringify(this.dataLimited))
        if(this.activeSort) return clonedData.sort((a, b) => {
          if(this.activeSort === 'slug') {
            return  this.sortAscending ? a.slug.localeCompare(b.slug) : b.slug.localeCompare(a.slug)
          }
          if(this.sortAscending) return a[this.activeSort] - b[this.activeSort]
          return b[this.activeSort] - a[this.activeSort]
        })
        else return clonedData
      },
      dataLimited: function () {
        const clonedData = JSON.parse(JSON.stringify(this.preSortedData))
        return clonedData.splice(0, this.numberOfItems);
      },
      preSortedData: function () {
        const clonedData = JSON.parse(JSON.stringify(this.tableData))
        return clonedData.sort((a, b) => b['averageNetDifference'] - a['averageNetDifference'])
      }
    }
  }
</script>

<style lang="scss" scoped>
  div.table-outer {
    margin-bottom: 100px;
  }
  button.show-more {
    border: 0;
    outline: none;
    cursor: pointer;
    width: 100%;
    max-width: 300px;
    padding: 20px 40px;
    margin: 10px 0 0 0;
    display: inline-block;
    background-color: #ffffff;
  }
  .table-header {
    filter: brightness(1.5);
    cursor: pointer;
  }
  .table {
    padding: 20px 0px;
    overflow-x: auto;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    color: #fff;
  }
  .row-outer {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    min-width: 960px;
  }
  .row-inner-container {
    width: 100%;
  }
  .row {
    min-width: 960px;
    display: flex;
    width: 100%;
    margin-bottom: 5px;
    .data {
      &:nth-of-type(odd) {
        background: linear-gradient(to right, darken(#00277C, 0) 0%, darken(#00277C, 5) 100%);
      }
      &:nth-of-type(even) {
        background: linear-gradient(to right, darken(#00277C, 0) 0%, darken(#00277C, 5) 100%);
      }
    }
    &.inner {
      .data {
        flex: 0 0 25%;
        &:nth-of-type(odd) {
          background: linear-gradient(to right, darken(#E71312, 10) 0%, darken(#E71312, 20) 100%);
        }
        &:nth-of-type(even) {
          background: linear-gradient(to right, darken(#E71312, 10) 0%, darken(#E71312, 20) 100%);
        }
      }
    }
  }
  .data {
    min-width: 25%;
    padding: 10px;
    box-sizing: border-box;
    line-height: 1.6em;
  }
  .slide-fade-enter-active {
    transition: all .3s ease;
  }
  .slide-fade-leave-active {
    transition: all .3s ease;
  }
  .slide-fade-enter, .slide-fade-leave-to
  /* .slide-fade-leave-active below version 2.1.8 */ {
    transform: scaleY(1);
    opacity: 0;
  }
</style>

