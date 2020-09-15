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
      <a class="lang-select" href="#">
        <img src="http://placehold.it/50" alt="">
      </a>
    </nav>
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
    data() {
      return { countries, bestValueClubs, bestTrophyClubs }
    },
  }
</script>

<style lang="scss" scoped>
  main {
    background-color: #141B2B;
    font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
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
    z-index: 100;
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
      border-radius: 50%;
      flex-shrink: 0;
      border: 2px solid #fff;
      overflow: hidden;
      width: 50px;
      height: 50px;
    }
  }
  .container {
    margin: 0 auto;
    padding: 0 30px;
    max-width: 1400px;
  }
</style>
