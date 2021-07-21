<template>
  <div class="partners">
    <h2 class="title">
      Proudly Supported By
    </h2>
    <div class="row">
      <div class="item">
        <a href="https://icetea.io/" target="_blank">
          <img alt="icetea labs" src="../assets/icetea.png"/>
        </a>
      </div>
      <div class="item">
        <a href="https://daomaker.com/" target="_blank">
          <img alt="dao maker" src="../assets/dao_maker.png"/>
        </a>
      </div>
    </div>
    <h2 class="title">
      Game Partners
    </h2>
    <div class="row">
      <div class="item">
        <a href="https://stephero.io/" target="_blank">
          <img alt="step hero" src="../assets/step_hero.png"/>
        </a>
      </div>
      <div class="item">
        <a href="https://kabyarena.com/" target="_blank">
          <img alt="kaby arena" src="../assets/kaby_arena.png"/>
        </a>
      </div>
      <div class="item">
        <a href="https://faraland.io/" target="_blank">
          <img alt="fara land" src="../assets/faraland.png"/>
        </a>
      </div>
    </div>
    <h2 class="title">
      Media Partners
    </h2>
    <div class="row">
      <div class="item">
        <a href="https://rarestone.capital/" target="_blank">
          <img alt="rare stone" src="../assets/rarestone.png"/>
        </a>
      </div>
      <div class="item">
        <a href="https://coinmarketcap.com/" target="_blank">
          <img alt="coin market cap" src="../assets/coin_market_cap.png"/>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Partners"
}
</script>

<style scoped>
  .partners {
    background: #0A0A0A;
    padding: var(--padding-article) var(--padding-section);
  }

  h2.title {
    font-weight: 700;
    font-size: 24px;
    line-height: 36px;
    color: var(--primary);
    margin-bottom: 24px;
  }

  h2.title:not(:first-child) {
    margin-top: 80px;
  }

  .row {
    display: flex;
    align-items: center;
  }

  .item {
    margin-right: 20px;
  }
</style>