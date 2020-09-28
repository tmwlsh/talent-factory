<template>
  <div>
    <div class="table">
      <div class="row-outer">
        <div class="row">
          <div class="data">Cristiano Ronaldo</div>
          <div class="data">Sporting CP</div>
          <div class="data">Market Value at join (A)</div>
          <div class="data">Market Value at point of sale / transfer / current value (B)</div>
        </div>
      </div>
      <div class="row-outer">
        <div class="row">
          <div class="data">Cristiano Ronaldo</div>
          <div class="data">Manchester United</div>
          <div class="data">Market Value at join (A)</div>
          <div class="data">Market Value at point of sale / transfer / current value (B)</div>
        </div>
      </div>
      <div class="row-outer">
        <div class="row">
          <div class="data">Cristiano Ronaldo</div>
          <div class="data">Real Madrid</div>
          <div class="data">Market Value at join (A)</div>
          <div class="data">Market Value at point of sale / transfer / current value (B)</div>
        </div>
      </div>
      <div class="row-outer">
        <div class="row">
          <div class="data">Cristiano Ronaldo</div>
          <div class="data">Juventus</div>
          <div class="data">Market Value at join (A)</div>
          <div class="data">Market Value at point of sale / transfer / current value (B)</div>
        </div>
      </div>
    </div>
  </div>
</template>

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
  .table-header {
    filter: brightness(1.5);
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
