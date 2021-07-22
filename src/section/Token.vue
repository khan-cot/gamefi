<template>
  <div id="token">
    <h1 class="title" >
      GFI Token Economy
    </h1>
    <div class="info slide">
      <div class="item slideLeft">
        <img alt src="../assets/bg1.png"/>
        <div class="detail">
          <h2>Discounts</h2>
          <p>GFI holders receive discounts on trading and yield fees.</p>
        </div>
      </div>
      <div class="item">
        <img alt src="../assets/bg2.png"/>
        <div class="detail">
          <h2>Liquidity Support</h2>
          <p>Portion of ecosystem fees are used to support the token’s liquidity on the secondary market.</p>
        </div>
      </div>
      <div class="item slideRight">
        <img alt src="../assets/bg3.png"/>
        <div class="detail">
          <h2>Governance</h2>
          <p>GFI stakers have the ability to propose the direction of the ecosystem.</p>
        </div>
      </div>
    </div>
    <h1 class="title">
      GameFi Supported
    </h1>
    <div class="info">
      <div class="item mr">
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
  font-weight: bold;
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
  background: #0A0A0A;
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
  font-weight: bold;
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
</style>