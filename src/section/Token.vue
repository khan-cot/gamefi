<template>
  <div id="token">
    <h1 class="title" >
      GAFI Token Economy
    </h1>
    <div class="info slide">
      <div class="item slideLeft">
        <img alt src="../assets/bg1.png"/>
        <img alt src="../assets/bg1_mb.png" class="mobile"/>
        <div class="detail">
          <h2>Discounts</h2>
          <p>GAFI holders receive discounts on trading and yield fees.</p>
        </div>
      </div>
      <div class="item">
        <img alt src="../assets/bg2.png"/>
        <img alt src="../assets/bg2_mb.png" class="mobile"/>
        <div class="detail">
          <h2>Liquidity Support</h2>
          <p>Portion of ecosystem fees are used to support the token’s liquidity on the secondary market.</p>
        </div>
      </div>
      <div class="item slideRight">
        <img alt src="../assets/bg3.png"/>
        <img alt src="../assets/bg3_mb.png" class="mobile"/>
        <div class="detail">
          <h2>Governance</h2>
          <p>GAFI stakers have the ability to propose the direction of the ecosystem.</p>
        </div>
      </div>
    </div>
    <h1 class="title">
      Supported By
    </h1>
    <div class="grid">
      <div class="item mr invert">
        <a href="https://icetea.io/" target="_blank">
          <img alt="icetea labs" src="../assets/icetea.png"/>
        </a>
      </div>
      <div class="item invert">
        <a href="https://daomaker.com/" target="_blank">
          <img alt="dao maker" src="../assets/dao_maker.png"/>
        </a>
      </div>
      <div class="item invert">
        <a href="https://polygon.technology/" target="_blank">
          <img alt="polygon" src="../assets/polygon.png"/>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Token"
}
</script>

<style scoped>
#token {
  margin-top: 100px;
  padding-top: 100px;
}

h1.title {
  background: url("../assets/token.png");
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

.info {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 240px;
}

.item {
  position: relative;
}

.bg-black {
  background: #0A0A0A;
}

.mobile {
  display: none;
}

.mr {
  margin-right: 20px;
}

.detail {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 80px 40px;
}

.detail h2 {
  margin-bottom: 20px;
  font-weight: 600;
  font-size: 32px;
  line-height: 40px;
}

.detail h2:before {
  content: '';
  position: absolute;
  top: 90px;
  left: 0;
  width: 6px;
  height: 14px;
  background: var(--primary);
}

.detail p {
  font-size: 18px;
  line-height: 28px;
  color: #D1D1D1;
}

.grid {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 240px;
}

.grid img {
  width: 360px;
}

@media screen and (max-width: 600px) {
  h1.title {
    background: url("../assets/token_mb.png");
    background-size: cover;
    aspect-ratio: 375/100;
    font-size: 28px;
    line-height: 36px;
  }

  .info {
    flex-direction: column;
    margin-bottom: 50px;
  }

  .item > img {
    display: none;
  }

  .item > img.mobile {
    display: block;
  }

  .detail h2 {
    margin-bottom: 12px;
    font-size: 20px;
    line-height: 28px;
  }

  .detail p {
    font-size: 14px;
    line-height: 22px;
  }

  .grid {
    padding: 20px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 4px;
    margin-bottom: 120px;
  }
}
</style>