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
      <a v-on:click={toggleLangSelector} href="../fr"><img src="~assets/flags/french.png" alt="French Flag" /></a>
    </div>
    <header>
      <div class="container">
        <div class="header-inner">
          <div class="header-text">
            <h1>Football Talent Factories</h1>
            <p>Which Clubs and Leagues Produce the Most World Class Talent?</p>
          </div>
        </div>
      </div>
    </header>

    <div class="page-intro">
      <div class="container">
        <div class="page-intro-inner">
          <p>We’ve taken the Top 100 male footballers in world football for each of the past 20 seasons and analysed their historic transfer market values and trophies won, by each club and league country played in.</p>
          <p>From this analysis, we can exclusively reveal the football talent factories of the world, that produce and elevate players to the next level.</p>
        </div>
      </div>
    </div>

    <div class="red-break first"></div>

    <div class="container">
      <div>
        <div id="countries">
          <h2 class="table-title">Best Countries to develop players</h2>
          <div class="table-intro">
            <p>To quote former England striker Gary Lineker, “Football is a simple game. Twenty-two men chase a ball for 90 minutes and at the end, the Germans always win”.</p>
            <p>And quite emphatically, this is the case for player development too. The ultimate decider of player skill and ability is their market value and the German Bundesliga is statistically the best for producing and enhancing footballing talent; adding £17.5m to players who play at least once in the German leagues.</p>
            <p class="bold">View the table below the explore the full data:</p>
          </div>
          <Table1 :table-data="countries"/>
        </div>
      </div>
    </div>

    <div class="red-break"></div>

    <div class="container">
      <div>
        <div id="value">
          <h2 class="table-title">Best Clubs to develop talent for value</h2>
          <div class="table-intro">
            <p>Based on our criteria of a minimum of 5 current or former top 100 rated players, Tottenham Hotspur is officially the best club one can play for to increase their market value. The quality of coaching at this club sees players increase their market value by an average of £32 million. The standout cases being Harry Kane (+£134m), Christian Eriksen (+£73.8m) and Gareth Bale (+£58.7m).</p>
            <p class="bold">View the table below the explore the full data:</p>
          </div>
          <Table2 :table-data="bestValueClubs"/>
        </div>
      </div>
    </div>

    <div class="red-break"></div>

    <div class="container">
      <div>
        <div id="trophies">
          <h2 class="table-title">Best clubs to develop talent for trophies</h2>
          <div class="table-intro">
            <p>And finally, which are the best clubs for producing trophy and title winners? Here we took the first senior club that players signed for and tracked every trophy won in the players lifetime career / career so far.</p>
            <p>As our list of players consists of the top 100 male players of the season for each of the past 20, we can also reveal the clubs who have recently been producing the best talent in world football.</p>
            <p>Ajax have produced the most top 100 rated male players in world football over the past 20 years, with a total of 11.</p>
            <p>Of the top 100 rated male players over the past 20 years, Barcelona have produced the most domestic title and UEFA Champions League winners, with players winning these trophies during their tenure at the Catalan giants or with other clubs (such as Thiago Alcantra at Bayern Munich and Pedro at Chelsea).</p>
          </div>
        </div>
      </div>
    </div>

    <div class="red-break"></div>

    <div class="container">
      <div>
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
            <p>All data accurate at time of release: January 2021.</p>
          </div>
        </div>
      </div>
      <div class="sbg-logo-container">
        <a target="_blank" href="https://pokerstars.com">
          <img src="~assets/poker-stars.png" alt="Poker Stars Logo" />
        </a>
      </div>
    </div>
  </main>
</template>

<script>
  import Table1 from '~/components/Table1'
  import Table2 from '~/components/Table2'
  import {countries, bestValueClubs} from '~/assets/data/real.json'


  export default {
    components: {
      Table1,
      Table2
    },
    data() {
      return {
        countries,
        bestValueClubs,
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
    font-family: 'Roboto', sans-serif;
  }
</style>

<style lang="scss" scoped>

  .sbg-logo-container {
    margin-top: 100px;
    text-align: center;

    a {
      display: inline-block;
      text-decoration: none;
      img {
        max-width: 160px;
      }
    }
  }

  .red-break {
    width: 100%;
    display: block;
    height: 5px;
    margin: 100px 0;
    background-color: #ffffff;
    &.first {
      margin: 0 0 100px 0;
    }
  }

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
    padding: 50px 0;
    text-align: center;
    background-color: #ffffff;
    div.page-intro-inner {
      max-width: 800px;
      margin: 0 auto;
    }
    p {
      color: #00194e;
      font-size: 16px;
      line-height: 1.6em;
    }
    @media all and (min-width: 768px){
      padding: 80px 0;
      p {
        font-size: 20px;
      }
    }
  }

  header {
    padding: 100px 0;
    background-image: url('~assets/header-bg2.jpg');
    background-size: cover;
    background-position: 50% 50%;
    .header-inner {
      .sbg-logo-container {
        margin-top: 0;
        margin-bottom: 40px;
      }
      div.header-text {
        max-width: 768px;
        margin: 0 auto;
        h1 {
          margin: 0 0 30px 0;
          color: #ffffff;
          font-size: 40px;
          display: block;
          text-align: center;
          font-family: 'Druk', sans-serif;
          text-transform: uppercase;
        }
        p {
          font-size: 18px;
          font-weight: 300;
          line-height: 1.6em;
          color: #ffffff;
          text-align: center;
        }
      }
      @media all and (min-width: 960px){
        div.header-text {
          h1 {
            font-size: 64px;
          }
          p {
            font-size: 24px;
          }
        }
      }
      @media all and (min-width: 1400px){
        div.header-text {
          h1 {
            font-size: 78px;
          }
          p {
            font-size: 32px;
          }
        }
      }
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
    background-color: darken(#E71312, 10);
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
    .sbg-logo-container {
      position: absolute;
      bottom: 30px;
      width: 100%;
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
    background: darken(#D70A0A, 5%);
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
    background-color: #000000;
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
    font-size: 2.2rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 0;
    color: #ffffff;
    font-family: 'Druk', sans-serif;
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
    background-color: #D70A0A;
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
      font-size: 24px;
      flex-shrink: 0;
      font-family: 'Druk', sans-serif;
      letter-spacing: 1px;
      line-height: 0.9em;
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
