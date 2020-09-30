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
      <div class="right-side">
        <div v-on:click='toggleHamb()' class="hamb" :class="hambOpen ? 'open' : 'closed'">
          <div class="line" />
          <div class="line" />
          <div class="line" />
        </div>
        <div v-on:click='toggleLangBlock()' class="lang-select">
          <img src="~assets/flags/english.png" alt="English Flag" />
        </div>
      </div>
    </nav>
    <div class="mobile-nav" :class="mobileNavOpen ? 'open' : 'closed'">
      <ul>
        <li v-on:click='hideMobileNav()'><a href="#countries" v-scroll-to="'#countries'">Best Countries to develop players</a></li>
        <li v-on:click='hideMobileNav()'><a href="#value"  v-scroll-to="'#value'">Best Clubs to develop talent for value</a></li>
        <li v-on:click='hideMobileNav()'><a href="#trophies"  v-scroll-to="'#trophies'">Best clubs to develop talent for trophies</a></li>
      </ul>
    </div>
    <div class="lang-select-block" :class="languageBlockOpen ? 'open' : 'closed'">
      <a v-on:click={toggleLangSelector} href="../de"><img src="~assets/flags/german.png" alt="German Flag" /></a>
      <a v-on:click={toggleLangSelector} href="../fr"><img src="~assets/flags/french.png" alt="French Flag" /></a>
      <a v-on:click={toggleLangSelector} href="../es"><img src="~assets/flags/spanish.png" alt="Spanish Flag" /></a>
    </div>
    <header>
      <div class="container">
        <div class="header-inner">
          <div class="header-text">
            <h1>Football Talent Factories</h1>
            <p>Which Clubs and Leagues Produce the Most World Class Talent?</p>
          </div>
          <div class="header-img-container">
            <img src="~assets/header-img.png" />
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <div class="page-intro">
        <p>We’ve taken the Top 100 male footballers in world football for each of the past 20 seasons and analysed their historic transfer market values and trophies won, by each club and league country played in.</p>
        <p>From this analysis, we can exclusively reveal the football talent factories of the world, that produce and elevate players to the next level.</p>
      </div>
      <div>
        <div id="countries">
          <h2 class="table-title">Best Countries to develop players</h2>
          <div class="table-intro">
            <p>To quote former England striker Gary Lineker, “Football is a simple game. Twenty-two men chase a ball for 90 minutes and at the end, the Germans always win”.</p>
            <p>And quite emphatically, this is the case for player development too. The ultimate decider of player skill and ability is their market value and the German Bundesliga is statistically the best for producing and enhancing footballing talent; adding £9.5m to players who play at least once in the German leagues.</p>
            <p>At the other end of the spectrum, the statistically worst country for football players to increase their market value in is China – with player market values declining by an average of £4.7m.</p>
            <p class="bold">View the table below the explore the full data:</p>
          </div>
          <Table1 :table-data="countries"/>
        </div>
        <div id="value">
          <h2 class="table-title">Best Clubs to develop talent for value</h2>
          <div class="table-intro">
            <p>Based on our criteria of a minimum of 5 players developed, RB Leipzig is officially the best club one can play for to increase their market value. The quality of coaching at this club sees players increase their market value by an average of £26 million. The standout cases being Timo Werner (+£64.8m), Naby Keita (+£42.3m) and Emil Forsberg (+£18.5m).</p>
            <p>Closely following behind in second place is Liverpool, with players increasing their market value by an average of £21.5m.</p>
            <p>To demonstrate the incredible impact Jurgen Klopp has had on the recent crop of Liverpool players, even world class players purchased for fees of £75m have seen their market value increase by £27m...</p>
            <p class="bold">View the table below the explore the full data:</p>
          </div>
          <Table2 :table-data="bestValueClubs"/>
        </div>
        <div id="trophies">
          <h2 class="table-title">Best clubs to develop talent for trophies</h2>
          <div class="table-intro">
            <p>And finally, which are the best clubs for producing trophy and title winners? Here we took the first senior club that players signed for and tracked every trophy won in the players lifetime career / career so far.</p>
            <p>As our list of players consists of the top 100 male players of the season for each of the past 20, we can also reveal the clubs who have recently been producing the best talent in world football.</p>
            <p class="bold">The results are as follows:</p>
            <ol>
              <li>Ajax and Real Madrid have produced the joint most top 100 rated male players in world football over the past 20 years, with 10 each. Before looking, can you guess them?</li>
              <li>Of the top 100 rated male players over the past 20 years, Barcelona have produced the most domestic title and UEFA Champions League winners, with players winning these trophies during their tenure at the Catalan giants or with other clubs (such as Thiago Alcantra at Bayern Munich and Pedro at Chelsea).</li>
            </ol>
            <p class="bold">View the table below the explore the full data:</p>
          </div>
          <Table3 :table-data="bestTrophyClubs"/>
        </div>
        <div id="methodology">
          <h2 class="table-title">Methodology</h2>
          <div class="table-intro">
            <p>For this study, we took the past 20 annualised lists of the top 100 male footballers of the year (as chosen by football experts from around the world) and reviewed the historic transfer market values of each player by their respective clubs and leagues played at.</p>
            <p>We did this to find the football talent factories that have a proven track record in transforming good players into greats, as the ultimate measure of player skill and ability is their transfer market value.</p>
            <p>Below is the analysis process we followed.</p>
            <p class="bold">Example Analysis Process: </p>
          </div>
          <Table4 />
          <div class="table-intro">
            <p>For consistency, all transfer market value data was sourced from Transfermarkt, so we could evaluate transfer market value increases/decreases during player loan periods and where players stayed at one club their whole career.</p>
            <p>To supplement the data analysis on player development, we also pulled in data on individual player honours per club to see which clubs and leagues had the most impact on developing serial winners.</p>
            <p>All data accurate at time of release: October 2020.</p>
          </div>
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
      return {
        countries,
        bestValueClubs,
        bestTrophyClubs,
        languageBlockOpen: false,
        hambOpen: false,
        mobileNavOpen: false
      };
    },
    methods: {
      toggleLangBlock () {
        this.languageBlockOpen = !this.languageBlockOpen;
      },
      toggleHamb () {
        this.hambOpen = !this.hambOpen;
        this.mobileNavOpen = !this.mobileNavOpen;
      },
      hideMobileNav () {
        this.mobileNavOpen = false;
        this.hambOpen = false;
      }
    }
  }
</script>

<style lang="scss">
  body {
    font-family: 'SSportsD';
  }
</style>

<style lang="scss" scoped>

  div#methodology {
    margin-top: 50px;
    @media all and (min-width: 768px){
      margin-top: 100px;
    }
  }

  div.table-intro {
    max-width: 1200px;
    margin: 0 auto;
    padding: 30px 0 0 0;
    p {
      font-family: Arial, Helvetica, sans-serif;
      color: rgba(#ffffff, 0.7);
      line-height: 1.6em;
      font-size: 16px;
      &.bold {
        color: rgba(#ffffff, 1);
        font-weight: 600;
      }
    }
    ol, ul {
      margin: 0;
      padding: 0 0 0 15px;
      li {
        padding: 0 0 0 10px;
        font-family: Arial, Helvetica, sans-serif;
        color: rgba(#ffffff, 1);
        line-height: 1.6em;
        font-size: 16px;
        margin-bottom: 20px;
        &:last-of-type {
          margin-bottom: 0;
        }
      }
    }
    @media all and (min-width: 768px){
      padding: 30px 0;
      p {
        font-size: 18px;
      }
      ol, ul {
        li {
          font-size: 18px;
        }
      }
    }
  }

  div.page-intro {
    padding: 0px 0 50px 0;
    text-align: center;
    margin: 0 auto;
    max-width: 768px;
    p {
      color: #ffffff;
      font-size: 18px;
      line-height: 1.6em;
    }
    @media all and (min-width: 768px){
      padding: 20px 0 80px 0;
    }
  }

  header {
    padding: 50px 0 0 0;
    margin-bottom: 100px;
    background-image: url('~assets/header-bg.jpg');
    background-size: cover;
    background-position: 50% 50%;
    .header-inner {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      .header-img-container {
        flex: 0 0 100%;
        display: block;
        img {
          width: 100%;
          height: auto;
        }
      }
      div.header-text {
        flex: 0 0 100%;
        h1 {
          margin: 0 0 30px 0;
          color: #ffffff;
          font-size: 40px;
          display: block;
          text-align: center;
        }
        p {
          font-size: 18px;
          font-weight: 300;
          line-height: 1.6em;
          color: #ffffff;
          text-align: center;
        }
      }
      @media all and (min-width: 768px){
        .header-img-container {
          flex: 0 0 400px;
        }
        div.header-text {
          flex: 0 0 calc(100% - 450px);
          h1 {
            text-align: left;
          }
          p {
            text-align: left;
          }
        }
      }
      @media all and (min-width: 960px){
        .header-img-container {
          flex: 0 0 600px;
        }
        div.header-text {
          flex: 0 0 calc(100% - 650px);
          h1 {
            font-size: 52px;
          }
        }
      }
      @media all and (min-width: 1400px){
        .header-img-container {
          flex: 0 0 700px;
        }
        div.header-text {
          flex: 0 0 calc(100% - 750px);
          h1 {
            font-size: 60px;
          }
        }
      }
    }
    @media all and (min-width: 768px){
      padding: 20px 0 0 0;
    }
  }

  div.mobile-nav {
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 100;
    position: fixed;
    transform: translateX(-100%);
    transition: .25s ease-in-out;
    background: linear-gradient(to right, darken(#E71312, 10) 0%, darken(#E71312, 20) 100%);
    &.open {
      transform: translateX(0);
    }
    ul {
      top: calc(50% + 10px);
      left: 50%;
      margin: 0;
      padding: 0;
      text-align: center;
      position: absolute;
      list-style-type: none;
      width: calc(100% - 60px);
      transform: translate(-50%, -50%);
      li {
        margin: 0 0 20px 0;
        padding: 0;
        display: block;
        list-style-type: none;
        a {
          padding: 10px;
          display: block;
          color: #ffffff;
          font-size: 24px;
          text-decoration: none;
        }
      }
    }
  }

  div.right-side {
    display: flex;
    align-items: center;
  }

  div.hamb {
    position: relative;
    display: block;
    width: 52px;
    height: 52px;
    margin-right: 20px;
    transition: .25s ease-in-out;
    div.line {
      left: 50%;
      height: 2px;
      width: 36px;
      position: absolute;
      background-color: #ffffff;
      transform: translateX(-50%);
      transition: .25s ease-in-out;
      &:nth-of-type(1){
        top: 15px;
      }
      &:nth-of-type(2){
        top: 25px;
      }
      &:nth-of-type(3){
        top: 35px;
      }
    }
    &.open {
      transform: rotate(180deg);
      div.line {
        &:nth-of-type(1){
          top: 25px;
          transform: translateX(-50%) rotate(-45deg);
        }
        &:nth-of-type(2){
          opacity: 0;
        }
        &:nth-of-type(3){
          top: 25px;
          transform: translateX(-50%) rotate(45deg);
        }
      }
    }
    @media all and (min-width: 960px){
      display: none;
    }
  }

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
    transition: .15s ease-in-out;
    box-shadow: 0 0 30px rgba(black, 0.8);
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
    background-color: darken(#00277C, 9);
    padding-bottom: 50px;
    @media all and (min-width: 768px){
      padding-bottom: 70px;
    }
    @media all and (min-width: 960px){
      padding-bottom: 100px;
    }
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
    box-shadow: 0 0 60px rgba(black, 0.3);
    justify-content: space-between;
    background: linear-gradient(to right, darken(#E71312, 10) 0%, darken(#E71312, 20) 100%);
    a {
      display: inline-block;
      color: #fff;
      text-decoration: none;
      text-transform: uppercase;
    }
    ul {
      margin: 0;
      padding: 0;
      display: none;
      justify-content: center;
      align-items: flex-start;
      list-style-type: none;
      a {
        padding: 10px;
        max-width: 180px;
        font-size: 14px;
      }
      @media all and (min-width: 960px){
        display: flex;
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
      @media all and (min-width: 768px){
        cursor: pointer;
      }
    }
  }

  .container {
    margin: 0 auto;
    padding: 0 30px;
    max-width: 1400px;
  }
</style>
