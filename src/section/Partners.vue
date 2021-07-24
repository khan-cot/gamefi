<template>
  <div class="partners">
    <h1 class="title">
      Partners
    </h1>
    <h2 class="title">
      Game Partners
    </h2>
    <div class="row">
      <div class="item invert">
        <a href="https://stephero.io/" target="_blank">
          <img alt="step hero" src="../assets/step_hero.png"/>
        </a>
      </div>
      <div class="item invert">
        <a href="https://kabyarena.com/" target="_blank">
          <img alt="kaby arena" src="../assets/kaby_arena.png"/>
        </a>
      </div>
      <div class="item invert">
        <a href="https://faraland.io/" target="_blank">
          <img alt="fara land" src="../assets/faraland.png"/>
        </a>
      </div>
    </div>
    <h2 class="title">
      Media Partners
    </h2>
    <div class="row">
      <div class="item invert">
        <a href="https://rarestone.capital/" target="_blank">
          <img alt="rare stone" src="../assets/rarestone.png"/>
        </a>
      </div>
      <div class="item invert">
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
    padding: var(--padding-article) var(--padding-section) 240px;
  }

  h1.title {
    background: url("../assets/partner.png");
    background-size: cover;
    aspect-ratio: 1440/231;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-weight: 600;
    font-size: 48px;
    line-height: 56px;
  }

  h2.title {
    font-weight: 600;
    font-size: 24px;
    line-height: 36px;
    color: var(--primary);
    margin-bottom: 32px;
    text-align: center;
    text-transform: uppercase;
  }
  .row {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .item {
    margin-right: 20px;
  }

  @media screen and (max-width: 600px) {
    .partners {
      padding-bottom: 120px;
    }

    h1.title {
      background: url("../assets/partner_mb.png");
      background-size: cover;
      aspect-ratio: 375/100;
      font-size: 28px;
      line-height: 36px;
    }

    h2.title {
        font-size: 16px;
        line-height: 28px;
        margin-bottom: 12px;
    }

    h2.title:not(:first-child) {
      margin-top: 20px;
    }

    .row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-gap: 4px;
    }
  }
</style>