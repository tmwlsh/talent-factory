<template>
  <main>
    <nav>
      <a href="#top" v-scroll-to="'body'" class="logo">Usines<br/>à talents</a>
      <ul>
        <li>
          <a href="#countries" v-scroll-to="'#countries'">Meilleurs pays pour le développement des joueurs</a>
          <a href="#value"  v-scroll-to="'#value'">Meilleurs clubs pour le développement de joueurs sur le marché</a>
          <a href="#trophies"  v-scroll-to="'#trophies'">Meilleurs clubs pour le développement des joueurs en championnats</a>
        </li>
      </ul>
      <div class="right-side">
        <div v-on:click='toggleHamb()' class="hamb" :class="hambOpen ? 'open' : 'closed'">
          <div class="line" />
          <div class="line" />
          <div class="line" />
        </div>
        <div v-on:click='toggleLangBlock()' class="lang-select">
          <img src="~assets/flags/french.png" alt="French Flag" />
        </div>
      </div>
    </nav>
    <div class="mobile-nav" :class="mobileNavOpen ? 'open' : 'closed'">
      <ul>
        <li v-on:click='hideMobileNav()'><a href="#countries" v-scroll-to="'#countries'">Meilleurs pays pour le développement des joueurs</a></li>
        <li v-on:click='hideMobileNav()'><a href="#value"  v-scroll-to="'#value'">Meilleurs clubs pour le développement de joueurs sur le marché</a></li>
        <li v-on:click='hideMobileNav()'><a href="#trophies"  v-scroll-to="'#trophies'">Meilleurs clubs pour le développement des joueurs en championnats</a></li>
      </ul>
      <div class="sbg-logo-container">
        <a target="_blank" href="https://skybet.com">
          <img src="~assets/sky-bet.png" alt="Sky Betting &amp; Gaming Logo" />
        </a>
      </div>
    </div>
    <div class="lang-select-block" :class="languageBlockOpen ? 'open' : 'closed'">
      <a v-on:click={toggleLangSelector} href="../en"><img src="~assets/flags/english.png" alt="English Flag" /></a>
      <a v-on:click={toggleLangSelector} href="../"><img src="~assets/flags/german.png" alt="German Flag" /></a>
      <a v-on:click={toggleLangSelector} href="../es"><img src="~assets/flags/spanish.png" alt="Spanish Flag" /></a>
    </div>
    <header>
      <div class="container">
        <div class="header-inner">
          <div class="header-text">
            <div class="sbg-logo-container">
              <a target="_blank" href="https://skybet.com">
                <img src="~assets/sky-bet.png" alt="Sky Betting &amp; Gaming Logo" />
              </a>
            </div>
            <h1>Football : les usines à talents</h1>
            <p>Quels clubs et championnats ont produit les plus grands talents du football?</p>
          </div>
        </div>
      </div>
    </header>
    <div class="page-intro">
      <div class="page-intro-inner">
        <div class="container">
          <p>Nous avons pris les 100 meilleurs footballeurs du monde pour chacune des 20 dernières saisons, et nous avons analysé l’historique de leurs valeurs sur le marché des transferts ainsi que les coupes remportées, par club et championnat dans lesquels ils ont évolué.</p>
          <p>En nous basant sur ces analyses, nous pouvons vous révéler en exclusivité quels clubs et championnats de football constituent de véritables usines à talents, qui façonnent les joueurs et leur permettent de passer au niveau supérieur.</p>
        </div>
      </div>
    </div>
    <div class="red-break first"></div>
    <div class="container">
      <div>
        <div id="countries">
          <h2 class="table-title">Meilleurs pays pour le développement des joueurs</h2>
          <div class="table-intro">
            <p>Comme le disait l’ancien attaquant anglais Gary Lineker, « le football est un jeu simple. Vingt-deux mecs courent après un ballon pendant 90 minutes et à la fin, ce sont toujours les Allemands qui gagnent ». Et ce pronostic se révèle tout aussi vrai en matière de développement des joueurs.</p>
            <p>La valeur d’un footballeur sur le marché des transferts constitue un indicateur de premier ordre pour évaluer les aptitudes et le potentiel de ce dernier. À ce titre, la Bundesliga est statistiquement le meilleur championnat en termes de production et d’amélioration des talents du ballon rond. En effet, les footballeurs de notre top 100 qui ont joué au moins une saison dans les ligues allemandes ont vu leur côte s’envoler de 10,3 millions d’euros.</p>
            <p>À l’opposé, le pays qui affiche les pires statistiques en la matière est la Chine, car nos joueurs y ont vu leur côte fondre de 5 millions d’euros en moyenne.</p>
            <p class="bold">Consultez le tableau ci-dessous pour voir l’intégralité des données:</p>
          </div>
          <Table1 :table-data="countries"/>
        </div>
      </div>
    </div>
    <div class="red-break"></div>
    <div class="container">
      <div>
        <div id="value">
          <h2 class="table-title">Meilleurs clubs pour le développement de joueurs sur le marché</h2>
          <div class="table-intro">
            <p>Pour cette analyse, nous avons étudié les clubs dont au minimum 5 joueurs avaient vu leur valeur augmenter sur le marché des transferts. Selon ce critère, le RB Leipzig est officiellement le meilleur club pour un joueur qui souhaiterait augmenter sa côte sur le mercato. La qualité du coaching dans ce club augmente la valeur des joueurs sur le marché de 28 millions d’euros en moyenne. Parmi les performances notables du club, Timo Werner (+70,3 millions d’euros), Naby Keita (+45,8 millions d’euros) et Emil Forsberg (+20 millions d’euros) signent des scores remarquables.</p>
            <p>Liverpool se classe en seconde position juste derrière le club allemand, avec une augmentation moyenne de la valeur de ses meilleurs joueurs de 23,3 millions d’euros.</p>
            <p>Pour démontrer l’impact incroyable de Jurgen Klopp sur les derniers joueurs recrutés par Liverpool, même les stars de classe mondiale achetées 81,3 millions d’euros ont vu leur valeur sur le marché des transferts augmenter de 29 millions d’euros.</p>
            <p class="bold">Consultez le tableau ci-dessous pour voir l’intégralité des données:</p>
          </div>
          <Table2 :table-data="bestValueClubs"/>
        </div>
      </div>
    </div>
    <div class="red-break"></div>
    <div class="container">
      <div>
        <div id="trophies">
          <h2 class="table-title">Meilleurs clubs pour le développement des joueurs en championnats</h2>
          <div class="table-intro">
            <p>Et pour terminer, quels sont les clubs qui arrivent le mieux à façonner des footballeurs qui remportent des coupes et des titres de champions ? Pour cette analyse, nous avons pris le premier club senior dans lequel les joueurs ont signé, et nous avons noté chaque coupe remportée pendant leur carrière ou à ce jour.</p>
            <p>Comme notre liste se compose des 100 meilleurs footballeurs de la saison pour chaque saison les 20 dernières années, nous sommes aussi en mesure de vous révéler quels sont les clubs qui ont récemment produit les meilleurs talents au monde de la planète football.</p>
            <p class="bold">Les résultats sont les suivants:</p>
            <ol>
              <li>Premiers à ex aequo, l’Ajax et le Real Madrid ont produit le plus grand nombre des 100 meilleurs joueurs de la scène footballistique internationale ces 20 dernières années, avec 10 footballeurs chacun. Seriez-vous capable de les citer sans regarder le détail des résultats?</li>
              <li>Des 100 meilleurs joueurs ces 20 dernières années, c’est le Barça qui a produit le plus grand nombre de joueurs ayant remporté des titres nationaux et des victoires en Champions League, les joueurs ayant gagné ces coupes lorsqu’ils évoluaient dans le club catalan, ou au sein d’autres club (comme Thiago Alcantra au Bayern de Munich et Pedro à Chelsea).</li>
            </ol>
            <p class="bold">Consultez le tableau ci-dessous pour voir l’intégralité des données:</p>
          </div>
          <Table3 :table-data="bestTrophyClubs"/>
        </div>
      </div>
    </div>
    <div class="red-break"></div>
    <div class="container">
      <div>
        <div id="methodology">
          <h2 class="table-title">Méthodologie</h2>
          <div class="table-intro">
            <p>Pour cette analyse, nous avons pris les 20 dernières listes annualisées des 100 meilleurs footballeurs de l’année (établies par des experts en football du monde entier), et nous avons étudié l’historique des valeurs de transfert de chaque joueur en fonction des clubs et championnats dans lesquels il a évolué.</p>
            <p>Nous avons procédé ainsi pour identifier les « usines » à talent du monde du football, qui ont prouvé leur capacité à transformer les bons joueurs en joueurs d’exception, dans la mesure où la valeur d’un footballeur sur le marché des transferts constitue un indicateur de choix pour évaluer les aptitudes et le potentiel de ce dernier.</p>
            <p>Vous trouverez ci-dessous l’analyse sur laquelle se basent nos affirmations.</p>
            <p class="bold">Exemple d’analyse:</p>
          </div>
          <Table4 />
          <div class="table-intro">
            <p>Pour une meilleure homogénéité des résultats, toutes les données relatives aux valeurs sur le marché des transferts sont issues de Transfermarkt. Ceci nous a permis d’évaluer les augmentations ou diminutions de la valeur sur le marché des transferts pendant les périodes de prêt des joueurs, et lorsque les joueurs sont restés dans le même club toute leur carrière. </p>
            <p>Pour compléter l’analyse des données concernant le développement des joueurs, nous avons également agrégé des informations relatives aux titres remportés par les joueurs par club pour voir quels clubs et championnats avaient le plus d’impact sur le développement de footballeurs titrés.</p>
            <p>Toutes les données sont exactes au moment de la publication : octobre 2020.</p>
          </div>
        </div>
      </div>
    </div>
    <div class="sbg-logo-container">
      <a target="_blank" href="https://skybet.com">
        <img src="~assets/sky-bet.png" alt="Sky Betting &amp; Gaming Logo" />
      </a>
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

  .sbg-logo-container {
    margin-top: 100px;
    text-align: center;
    a {
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
    background-color: #fff;
    &.first {
        margin: 0 0 100px;
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
    margin: 0 auto;
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
    text-align: center;
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
        }
        p {
          font-size: 18px;
          font-weight: 300;
          line-height: 1.6em;
          color: #ffffff;
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
            font-size: 72px;
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
    .sbg-logo-container {
      position: absolute;
      width: 100%;
      text-align: center;
      bottom: 40px;
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
    padding: 85px 23px 6px 19px;
    transform: translateY(-100%);
    transition: .15s ease-in-out;
    box-shadow: 0 0 30px rgba(black, 0.8);
    background: linear-gradient(to right, #1D3C80 0%, #193573 100%);
    @media all and (min-width: 960px){
      padding: 115px 23px 6px 19px;
    }
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
    background-color: darken(#E71312, 10);
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
      li {
        display: flex;
        align-items: center;
      }
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
