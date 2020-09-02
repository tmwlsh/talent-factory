<template>
  <main>
    <div class="container">
      <div>
        <p>Countries</p>
        <Table1 :table-data="countries"/>
        <p>Best value clubs</p>
        <Table1 :table-data="bestValueClubs"/>
        <p>Best trophy clubs</p>
        <Table2 :table-data="bestTrophyClubs"/>
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
    },
    data() {
      return { countries, bestValueClubs, bestTrophyClubs }
    },
  }
</script>

<style lang="scss" scoped>
  main {
    background-color: #080e40;
  }
  .container {
    color: #fff;
    padding: 40px;
    max-width: 1180px;
    margin: 0 auto;
  }
</style>
