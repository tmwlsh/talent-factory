<template>
  <main>
    <nav>
      <a href="#top" v-scroll-to="'body'" class="logo">Talent <br/> Factories</a>
      <ul>
        <li>
          <a href="#countries" v-scroll-to="'#countries'">Best Countries to develop players</a>
          <a href="#value"  v-scroll-to="'#value'">Best Clubs to develop talent for value</a>
          <a href="#trophies"  v-scroll-to="'#trophies'">Best clubs to develop talent for trophies</a>
        </li>
      </ul>
      <div v-on:click='toggleLangBlock()' class="lang-select">
        <img src="~assets/flags/german.png" alt="German Flag" />
      </div>
    </nav>
    <div class="lang-select-block" :class="languageBlockOpen ? 'open' : 'closed'">
      <a v-on:click={toggleLangSelector} href="#"><img src="~assets/flags/german.png" alt="German Flag" /></a>
      <a v-on:click={toggleLangSelector} href="#"><img src="~assets/flags/english.png" alt="British Flag" /></a>
      <a v-on:click={toggleLangSelector} href="#"><img src="~assets/flags/french.png" alt="French Flag" /></a>
      <a v-on:click={toggleLangSelector} href="#"><img src="~assets/flags/spanish.png" alt="Spanish Flag" /></a>
    </div>
    <div class="container">
      <div>
        <div id="countries">
          <h2 class="table-title">Best Countries to develop players</h2>
          <Table1 :table-data="countries"/>
        </div>
        <h2 class="quote">
          Playing in Spain could increase your value by up to 1,500%
        </h2>
        <div id="value">
          <h2 class="table-title">Best Clubs to develop talent for value</h2>
          <Table1 :table-data="bestValueClubs"/>
        </div>
        <div class="right">
          <h2 class="quote right">
            Playing for Liverpool could increase your net value by up to &pound;20,000,000
          </h2>
        </div>
        <div id="trophies">
          <h2 class="table-title">Best clubs to develop talent for trophies</h2>
          <Table2 :table-data="bestTrophyClubs"/>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
  import Table1 from '~/components/Table1'
  import Table2 from '~/components/Table2'
  import {countries, bestValueClubs, bestTrophyClubs} from '~/assets/data/real.json'


  export default {
    components: {
      Table1,
      Table2
    },
    data: {
      languageBlockOpen: false
    },
    data() {
      return { countries, bestValueClubs, bestTrophyClubs };
    },
    methods: {
      toggleLangBlock () {
        this.languageBlockOpen = !this.languageBlockOpen;
        console.log(this.languageBlockOpen);
      }
    }
  }
</script>

<style lang="scss" scoped>
  .lang-select-block {
    top: 0;
    right: 0;
    z-index: 150;
    height: auto;
    display: flex;
    position: fixed;
    flex-wrap: wrap;
    flex-direction: column;
    justify-content: center;
    padding: 80px 23px 6px 19px;
    transform: translateY(-100%);
    background: linear-gradient(to right, #1D3C80 0%, #193573 100%);
    &.open {
      transform: translateY(0);
    }
    a {
      display: block;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      margin-bottom: 10px;
      position: relative;
      &:after {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border: 2px solid #ffffff;
        pointer-events: none;
        content: '';
        z-index: 100;
        border-radius: 50%;
      }
      img {
        display: block;
        position: relative;
        width: calc(100% + 4px);
        height: calc(100% + 4px);
      }
    }
  }
  main {
    background-color: #141B2B;
  }
  .table-header {
    filter: brightness(1.5);
  }
  .table-title {
    text-align: center;
    font-size: 1.4rem;
    text-transform: uppercase;
    margin-bottom: 0;
    color: #ffffff;
  }
  .quote {
    font-size: 3rem;
    max-width: 15em;
    color: #9EADD0;
    margin-bottom: 0;
    padding: 100px 0px;
    margin-top: 0;
  }
  .right {
    display: flex;
    justify-content: flex-end;
    text-align: right;
  }
  nav {
    top: 0;
    z-index: 200;
    display: flex;
    position: sticky;
    padding: 10px 20px;
    align-items: center;
    justify-content: space-between;
    background: linear-gradient(to right, #9D2627 0%, #7E1E1D 100%);
    a {
      display: inline-block;
      color: #fff;
      text-decoration: none;
      text-transform: uppercase;
    }
    ul {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      list-style-type: none;
      a {
        padding: 10px;
        max-width: 180px;
        font-size: 14px;
      }
    }
    .logo {
      text-transform: uppercase;
      font-weight: 700;
      font-size: 20px;
      flex-shrink: 0;
    }
    .lang-select {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      border: 2px solid #fff;
      position: relative;
      overflow: hidden;
      img {
        top: -2px;
        left: -2px;
        display: block;
        position: relative;
        width: calc(100% + 4px);
      }
    }
  }
  .container {
    margin: 0 auto;
    padding: 0 30px;
    max-width: 1400px;
  }
</style>
