<template>
  <main>
    <nav>
      <a href="#top" v-scroll-to="'body'" class="logo">Talent <br/> Factories</a>
      <ul>
        <li>
          <a href="#countries" v-scroll-to="'#countries'">Países en los que mejor evolucionan los futbolistas</a>
          <a href="#value"  v-scroll-to="'#value'">Clubes en los que más aumenta el valor de los jugadores</a>
          <a href="#trophies"  v-scroll-to="'#trophies'">Clubes que más ganadores de títulos producen</a>
        </li>
      </ul>
      <div class="right-side">
        <div v-on:click='toggleHamb()' class="hamb" :class="hambOpen ? 'open' : 'closed'">
          <div class="line" />
          <div class="line" />
          <div class="line" />
        </div>
        <div v-on:click='toggleLangBlock()' class="lang-select">
          <img src="~assets/flags/spanish.png" alt="Spanish Flag" />
        </div>
      </div>
    </nav>
    <div class="mobile-nav" :class="mobileNavOpen ? 'open' : 'closed'">
      <ul>
        <li v-on:click='hideMobileNav()'><a href="#countries" v-scroll-to="'#countries'">Países en los que mejor evolucionan los futbolistas</a></li>
        <li v-on:click='hideMobileNav()'><a href="#value"  v-scroll-to="'#value'">Clubes en los que más aumenta el valor de los jugadores</a></li>
        <li v-on:click='hideMobileNav()'><a href="#trophies"  v-scroll-to="'#trophies'">Clubes que más ganadores de títulos producen</a></li>
      </ul>
    </div>
    <div class="lang-select-block" :class="languageBlockOpen ? 'open' : 'closed'">
      <a v-on:click={toggleLangSelector} href="../en"><img src="~assets/flags/english.png" alt="English Flag" /></a>
      <a v-on:click={toggleLangSelector} href="../"><img src="~assets/flags/german.png" alt="German Flag" /></a>
      <a v-on:click={toggleLangSelector} href="../fr"><img src="~assets/flags/french.png" alt="French Flag" /></a>
    </div>
    <header>
      <div class="container">
        <div class="header-inner">
          <div class="header-text">
            <h1>Fábricas de talento futbolístico</h1>
            <p>¿Qué clubes y ligas producen los futbolistas con más talento de todo el mundo?</p>
          </div>
          <div class="header-img-container">
            <img src="~assets/header-img.png" />
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <div class="page-intro">
        <p>Nos hemos fijado en los 100 mejores futbolistas de las 20 últimas temporadas y hemos analizado su valor de mercado y los trofeos que han ganado en función del club y de la liga.</p>
        <p>Gracias a este análisis, podemos revelar en exclusiva cuáles son las fábricas de talento futbolístico, aquellas que producen jugadores y los impulsan al siguiente nivel.</p>
      </div>
      <div>
        <div id="countries">
          <h2 class="table-title">Países en los que mejor evolucionan los futbolistas</h2>
          <div class="table-intro">
            <p>Ya lo dijo el exfutbolista inglés Gary Lineker: "El fútbol es un deporte muy sencillo. Veintidós hombres persiguen una pelota durante 90 minutos y, al final, Alemania siempre gana".</p>
            <p>Pues bien, curiosamente, ocurre lo mismo en relación con la evolución de los jugadores. El factor fundamental que indica la calidad de un jugador es su valor en el mercado, y según los datos, la Bundesliga alemana es la que más talento futbolístico produce e impulsa, ya que suma una media de 9,5 millones de libras al valor de los futbolistas que juegan en ella al menos una vez.</p>
            <p>Por el contrario, el país en el que los jugadores lo tienen más difícil para aumentar su valor de mercado es China, donde pierden una media de 4,7 millones de libras.</p>
            <p class="bold">Consulta la siguiente tabla para ver todos los datos:</p>
          </div>
          <Table1 :table-data="countries"/>
        </div>
        <div id="value">
          <h2 class="table-title">Clubes en los que más aumenta el valor de los jugadores</h2>
          <div class="table-intro">
            <p>Con un mínimo que hemos establecido en 5 jugadores formados, el R. B. Leipzig es la mejor opción si un jugador quiere aumentar su valor de mercado, pues la calidad del entrenamiento de este club hace que los jugadores aumenten su valor una media de 26 millones de libras. Destacan jugadores como Timo Werner (+64,8 millones de libras), Naby Keïta (+42,3 millones de libras) y Emil Forsberg (+18,5 millones de libras).</p>
            <p>La segunda mejor opción es el Liverpool, donde los jugadores aumentan su valor de mercado una media de 21,5 millones de libras. Sube incluso el valor de jugadores de primer nivel que fueron comprados por 75 millones de libras y, ahora, cuestan 27 millones de libras más, lo que demuestra el asombroso efecto que ha tenido Jurgen Klopp en la plantilla.</p>
            <p class="bold">Consulta la siguiente tabla para ver todos los datos:</p>
          </div>
          <Table2 :table-data="bestValueClubs"/>
        </div>
        <div id="trophies">
          <h2 class="table-title">Clubes que más ganadores de títulos producen</h2>
          <div class="table-intro">
            <p>¿Qué clubes son los mejores a la hora de producir ganadores de títulos? En este caso, nos hemos fijado en el primer club sénior con el que un jugador firma un contrato y, después, hemos comprobado todos los títulos ganados por ese jugador durante su carrera.</p>
            <p>Los datos abarcan 20 temporadas e incluyen los 100 mejores jugadores de cada temporada, así que también podemos saber los clubes en donde se ha producido más talento en los últimos años.</p>
            <p class="bold">Los resultados son los siguientes:</p>
            <ol>
              <li>El Ajax y el Real Madrid, con 10 jugadores cada uno, son los clubes que más futbolistas aportan a la lista de los 100 mejores jugadores en los últimos 20 años. Sin mirar, ¿quieres intentar adivinarlos?</li>
              <li>A los 100 mejores jugadores de los últimos 20 años, el Barcelona aporta la mayor cantidad de ganadores de títulos nacionales y de la Champions. Los jugadores han ganado los títulos jugando en el Barcelona o en otros clubes (por ejemplo, Thiago Alcántara en el Bayern de Múnich o Pedro en el Chelsea).</li>
            </ol>
            <p class="bold">Consulta la siguiente tabla para ver todos los datos:</p>
          </div>
          <Table3 :table-data="bestTrophyClubs"/>
        </div>
        <div id="methodology">
          <h2 class="table-title">Metodología</h2>
          <div class="table-intro">
            <p>En este estudio, hemos analizado las listas de los 100 mejores jugadores de la temporada de los últimos 20 años (elegidos por expertos futbolísticos de todo el mundo) y hemos comprobado el valor de mercado de cada jugador en función de los clubes y las ligas en donde jugaron.</p>
            <p>Nuestro objetivo es averiguar qué clubes han transformado a los buenos jugadores en excelentes (el factor fundamental que indica la calidad de un jugador es su valor en el mercado).</p>
            <p>A continuación, se muestra el análisis que hemos realizado.</p>
            <p class="bold">Análisis de ejemplo:</p>
          </div>
          <Table4 />
          <div class="table-intro">
            <p>Todos los valores de mercado se han obtenido de Transfermarkt. Hemos comprobado las subidas y bajadas del valor de los jugadores durante las cesiones y en el caso de que se quedasen en un club toda su carrera.</p>
            <p>Para complementar el análisis de datos sobre la evolución de los jugadores, también hemos obtenido datos sobre los títulos ganados en función del club. Así, se puede comprobar qué clubes y ligas han tenido más influencia a la hora de producir grandes ganadores.</p>
            <p>Los datos son precisos en el momento de la publicación (octubre de 2020).</p>
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
