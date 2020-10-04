<template>
  <main>
    <nav>
      <a href="#top" v-scroll-to="'body'" class="logo">Talent <br/> Factories</a>
      <ul>
        <li>
          <a href="#countries" v-scroll-to="'#countries'">Die Länder mit der besten Ausbildung für Spieler</a>
          <a href="#value"  v-scroll-to="'#value'">Clubs mit dem besten Effekt auf den Marktwert der Spieler</a>
          <a href="#trophies"  v-scroll-to="'#trophies'">Clubs mit den meisten Trophäen</a>
        </li>
      </ul>
      <div class="right-side">
        <div v-on:click='toggleHamb()' class="hamb" :class="hambOpen ? 'open' : 'closed'">
          <div class="line" />
          <div class="line" />
          <div class="line" />
        </div>
        <div v-on:click='toggleLangBlock()' class="lang-select">
          <img src="~assets/flags/german.png" alt="German Flag" />
        </div>
      </div>
    </nav>
    <div class="mobile-nav" :class="mobileNavOpen ? 'open' : 'closed'">
      <ul>
        <li v-on:click='hideMobileNav()'><a href="#countries" v-scroll-to="'#countries'">Die Länder mit der besten Ausbildung für Spieler</a></li>
        <li v-on:click='hideMobileNav()'><a href="#value"  v-scroll-to="'#value'">Clubs mit dem besten Effekt auf den Marktwert der Spieler</a></li>
        <li v-on:click='hideMobileNav()'><a href="#trophies"  v-scroll-to="'#trophies'">Clubs mit den meisten Trophäen</a></li>
      </ul>
      <div class="sbg-logo-container">
        <a target="_blank" href="https://skybet.com">
          <img src="~assets/sky-bet.png" alt="Sky Betting &amp; Gaming Logo" />
        </a>
      </div>
    </div>
    <div class="lang-select-block" :class="languageBlockOpen ? 'open' : 'closed'">
      <a v-on:click={toggleLangSelector} href="./en"><img src="~assets/flags/english.png" alt="English Flag" /></a>
      <a v-on:click={toggleLangSelector} href="./es"><img src="~assets/flags/spanish.png" alt="Spanish Flag" /></a>
      <a v-on:click={toggleLangSelector} href="./fr"><img src="~assets/flags/french.png" alt="French Flag" /></a>
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
            <h1>Talentschmieden im Fußball</h1>
            <p>Welche Clubs und Ligen bringen die meisten Ausnahmespieler hervor?</p>
          </div>
        </div>
      </div>
    </header>
    <div class="page-intro">
      <div class="page-intro-inner">
        <div class="container">
          <p>Wir haben uns die Top-100 der weltweit besten männlichen Fußballspieler näher angeschaut und je nach Club und Liga ihre Transfermarktwerte und Trophäen analysiert, die sie in den letzten 20 Saisons erzielt bzw. gewonnen haben.</p>
          <p>Dank dieser Analyse können wir einen exklusiven Einblick in die Fußball Talentschmieden der Welt geben, die die Fähigkeiten der Spieler beflügeln.</p>
        </div>
      </div>
    </div>
    <div class="red-break first"></div>
    <div class="container">
      <div>
        <div id="countries">
          <h2 class="table-title">Die Länder mit der besten Ausbildung für Spieler</h2>
          <div class="table-intro">
            <p>Um den ehemaligen Stürmer der Englänger Gary Lineker zu zitieren: "Fußball ist ein simples Spiel. 22 Spieler jagen über 90 Minuten dem Ball nach - und am Ende gewinnen immer die Deutschen."</p>
            <p>Und ganz eindeutig trifft das auch auf das Training der Spieler zu. Der beste Indikator für die Fähigkeiten der Spieler ist ihr Marktwert. Und die deutsche Bundesliga produziert und veredelt die meisten Fußballtalente. Der Wert von Spielern steigt um 10,3 Millionen Euro, wenn Sie mindestens einmal in einer der deutschen Ligen antreten.</p>
            <p>Am unteren Ende des Spektrums finden sich die Länder, die sich statistisch betrachtet am schlechtesten auf den Marktwert auswirken. Angeführt von China, wo der Wert der Spieler durchschnittlich um 5,10 Millionen Euro sinkt.</p>
            <p class="bold">In der Tabelle unten finden Sie eine vollständige Liste der Daten:</p>
          </div>
          <Table1 :table-data="countries"/>
        </div>
      </div>
    </div>
    <div class="red-break"></div>
    <div class="container">
      <div>
        <div id="value">
          <h2 class="table-title">Clubs mit dem besten Effekt auf den Marktwert der Spieler</h2>
          <div class="table-intro">
            <p>Geht man von unserem Kriterium, dass 5 Spieler ausgebildet werden, aus, wirkt sich RB Leipzig offiziell am besten auf den Marktwert aus. Die Qualität des Trainings sorgt bei diesem Club dafür, dass der Wert der Spieler durchschnittlich um 28,2 Millionen Euro steigt. Besonders extreme Fälle sind Timo Werner (+70,3 Millionen Euro), Naby Keita (+45,9 Millionen Euro) und Emil Forsberg (+20,1 Millionen Euro).</p>
            <p>Mit knappem Rückstand liegt Liverpool auf dem zweiten Platz. Hier steigt der Marktwert der Spieler durchschnittlich um 23,3 Millionen Euro.</p>
            <p>Ein guter Beleg für den erstaunlichen Effekt, den Jürgen Klopp auf das Team Liverpool hat: Selbst bei Weltklassespielern, die für 81 Millionen Euro eingekauft wurden, steigert sich der Marktwert um 30 Millionen Euro...</p>
            <p class="bold">In der Tabelle unten finden Sie eine vollständige Liste der Daten:</p>
          </div>
          <Table2 :table-data="bestValueClubs"/>
        </div>
      </div>
    </div>
    <div class="red-break"></div>
    <div class="container">
      <div>
        <div id="trophies">
          <h2 class="table-title">Clubs mit den meisten Trophäen</h2>
          <div class="table-intro">
            <p>Und zu guter letzt: Aus welchen Clubs kommen die Spieler, die die meisten Trophäen und Titel gewinnen? Um das zu ermitteln, sind wir vom ersten bedeutenderen Club ausgegangen, der die Spieler unter Vertrag genommen hat. Davon ausgehend haben wir jede Trophäe aufgelistet, die die Fußballer in ihrer gesamten Karriere bzw. in ihrer Karriere bis jetzt gewonnen haben.</p>
            <p>Da unsere Liste die Top-100 der männlichen Spieler aus den vergangenen 20 Saisons enthält, können wir auch die Clubs identifizieren, die in der letzten Zeit die meisten Weltklassespieler produziert haben.</p>
            <p class="bold">Das sind die Ergebnisse:</p>
            <ol>
              <li>Ajax und Real Madrid haben in den letzten 20 Jahren zusammen die meisten der Top-100 Talente des Männerfußball trainiert - 10 Stück pro Team. Wollen Sie raten, bevor wir sie aufdecken?</li>
              <li>Unter der Top-100 der männlichen Spieler aus den letzten 20 Jahren hat Barcelona die Talente produziert, die die meisten Landes und UEFA Tittel gewonnen haben. Die Fußballer haben diese Titel während ihrer Zeit bei den Catalan Giants oder in anderen Clubs gewonnen (z. B. Thiago Alcantra bei Bayern München, Pedro bei Chelsea).</li>
            </ol>
            <p class="bold">In der Tabelle unten finden Sie eine vollständige Liste der Daten:</p>
          </div>
          <Table3 :table-data="bestTrophyClubs"/>
        </div>
      </div>
    </div>
    <div class="red-break"></div>
    <div class="container">
      <div>
        <div id="methodology">
          <h2 class="table-title">Vorgehensweise</h2>
          <div class="table-intro">
            <p>Für unsere Statistik haben wir uns die letzten 20 Jahreslisten der Top-100 der männlichen Fußballer des Jahres (von Fußballexperten weltweit gewählt) näher angesehen und dabei den zu dem jeweiligen Zeitpunkt geltenden Transfermarktwert jedes Spieler nach Club und Liga ermittelt.</p>
            <p>So wollten wir die Talentschmieden im Fußballsport identifizieren, die Erfolge darin vorzeigen können, gute Spiele in großartige zu entwickeln, da der beste Indikator der Fähigkeiten der Transfermarktwert ist.</p>
            <p>Weiter unten finden Sie die einzelnen Schritte, denen wir bei jeder Analyse gefolgt sind.</p>
            <p class="bold">Beispiel für eine Analyse:</p>
          </div>
          <Table4 />
          <div class="table-intro">
            <p>Um der Folgerichtigkeit willen haben wir alle Daten über die Transfermarktwerte von Transfermarkt bezogen. So konnten wir den Anstieg/Rückgang des Werts bei Leihspielern und bei Fußballern, die ihre gesamte Karriere in einem Club verbracht haben, bewerten.</p>
            <p>Zusätzlich zu der Daten gestützten Analyse der Entwicklung der Spieler ließen wir in die Bewertung auch Daten über einzelne Spieler, je nach Club kategorisiert, einfließen. So konnten wir feststellen, welche Clubs und Ligen die Fußballer mit den meisten Siegen produzieren.</p>
            <p>Alle Daten sind bis zum Zeitpunkt der Veröffentlichung gültig: Oktober 2020.</p>
          </div>
          <div class="sbg-logo-container">
            <a target="_blank" href="https://skybet.com">
              <img src="~assets/sky-bet.png" alt="Sky Betting &amp; Gaming Logo" />
            </a>
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
      padding: 100px 23px 6px 19px;
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
