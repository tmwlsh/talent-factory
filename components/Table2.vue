<template>
  <div>
    <div class="table">
      <div class="table-header row">
        <div class="data" @click.prevent="setActiveSort('slug')">First Club</div>
        <div class="data" @click.prevent="setActiveSort('playerCount')">First club Count</div>
        <div class="data" @click.prevent="setActiveSort('domesticTitles')">Domestic Titles</div>
        <div class="data" @click.prevent="setActiveSort('ucls')">Champtions league wins</div>
        <div class="data" @click.prevent="setActiveSort('uel')">Eurpoa league wins</div>
        <div class="data" @click.prevent="setActiveSort('domesticCups')">Domestic Cups</div>
        <div class="data" @click.prevent="setActiveSort('domesticSecondCups')">Domestic Second cups</div>
      </div>
      <div class="row-outer" v-for="row in dataLimited" :key="row.country">
        <div class="row" @click.prevent="toggleDisplay(row.slug)">
          <div class="data">
            {{row.name}}
          </div>
          <div class="data">
            {{row.playerCount}}
          </div>
          <div class="data">
            {{row.domesticTitles}}
          </div>
          <div class="data">
            {{row.ucls}}
          </div>
          <div class="data">
            {{row.uel}}
          </div>
          <div class="data">
            {{row.domesticCups}}
          </div>
          <div class="data">
            {{row.domesticSecondCups}}
          </div>
        </div>
        <transition name="slide-fade">
          <div v-if="activeCountries.indexOf(row.slug) !== -1">
            <div class="row inner" v-for="player in row.data" :key="player.player">
              <div class="data">
                {{player.name}}
              </div>
              <div class="data">
                {{player.playerCount}}
              </div>
              <div class="data">
                {{player.domesticTitles}}
              </div>
              <div class="data">
                {{player.ucls}}
              </div>
              <div class="data">
                {{player.uel}}
              </div>
              <div class="data">
                {{player.domesticCups}}
              </div>
              <div class="data">
                {{player.domesticSecondCups}}
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
        if(this.numberOfItems >= this.filteredTableData.length) {
          this.numberOfItems = this.filteredTableData.length;
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
        return `£${num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",")}`;
      }
    },
    computed: {
      filteredTableData: function () {
        const clonedData = JSON.parse(JSON.stringify(this.tableData))
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
        const clonedData = JSON.parse(JSON.stringify(this.tableData))
        return clonedData.splice(0, this.numberOfItems);
      }
    }
  }
</script>

<style lang="scss" scoped>
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
  .table {
    padding: 20px 0px;
    overflow-x: auto;
    color: #fff;
  }
  .row {
    display: flex;
    margin-bottom: 5px;
    .data {
      &:nth-of-type(odd) {
        background: linear-gradient(to right, #162C5F 0%, #122854 100%);
      }
      &:nth-of-type(even) {
        background: linear-gradient(to right, #1D3C80 0%, #193573 100%);
      }
    }
    &.inner {
      .data {
        &:nth-of-type(odd) {
          background: linear-gradient(to right, #721C1D 0%, #5D1515 100%);
        }
        &:nth-of-type(even) {
          background: linear-gradient(to right, #9D2627 0%, #7E1E1D 100%);
        }
      }
    }
  }
  .data {
    min-width: 250px;
    padding: 10px;
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
  .show-more {
    width: 100%;
    position: sticky;
    left: 0;
  }
</style>

