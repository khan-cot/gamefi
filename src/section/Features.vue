<template>
  <div id="features">
    <div class="features">
      <div class="features-title">
        <h1>Ecosystem Features</h1>
        <div>GameFi offers the most extensive collection of resources to all participants in the booming game finance economy.</div>
      </div>
      <div class="feature-grid">
        <div class="feature-item fade">
          <img alt src="../assets/accelerator.svg"/>
          <div class="title">Game Aggregator</div>
          <div class="detail">Access games and gaming assets of any blockchain from a single user dashboard.</div>
        </div>
        <div class="feature-item fade">
          <img alt src="../assets/market.svg"/>
          <div class="title">Game Market</div>
          <div class="detail">Multi-chain NFT marketplace exclusively for blockchain game items.</div>
        </div>
        <div class="feature-item fade">
          <img alt src="../assets/rocket.svg"/>
          <div class="title">Game Launchpad</div>
          <div class="detail">The only game-specific launchpad, designed to be chain-agnostic.</div>
        </div>
        <div class="feature-item fade">
          <img alt src="../assets/exchange.svg"/>
          <div class="title">Yield Swaps</div>
          <div class="detail">Token holders can finance Play to Earn gameplay through a swap platform.</div>
        </div>
        <div class="feature-item fade">
          <img alt src="../assets/gamepad.svg"/>
          <div class="title">Minigames</div>
          <div class="detail">Simple blockchain games to help new crypto adopters get acquainted with NFTs and Play to Earn models.</div>
        </div>
      </div>
    </div>
    <div class="fees">
      <h1 class="fee-title"><span>Ecosystem</span> Fees</h1>
      <div class="fee-list">
        <div class="fee-item">
          <div>Trading Fees</div>
          <div>Trading Fees are applied to item trades that take place on the Game Market.</div>
        </div>
        <div class="fee-item">
          <div>Acceleration Fees</div>
          <div>Acceleration Fees are applied to funds raised on the Game Launchpad and for smart contracts deployed from
            the GameFi accelerator.
          </div>
        </div>
        <div class="fee-item">
          <div>Yield Fees</div>
          <div>Yield Fees are earned from the Play to Earn financed through the Yield Swaps.</div>
        </div>
      </div>
      <div class="fee-image">
        <img alt src="../assets/image3.png"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Features"
}
</script>

<style scoped>
#features {
  margin-top: 100px;
  padding-top: 100px;
}

.features-title {
  background: url("../assets/features.png");
  background-size: cover;
  aspect-ratio: 1440/231;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.features-title h1 {
  font-weight: 600;
  font-size: 48px;
  line-height: 56px;
}

.features-title div {
  margin-top: 20px;
  width: 750px;
  font-size: 22px;
  line-height: 32px;
  color: #D1D1D1;
}

.feature-grid {
  padding: 40px var(--padding-section);
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 60px;
}

.feature-item:nth-child(3n+2) {
  transition-delay: 0.2s;
}

.feature-item:nth-child(3n) {
  transition-delay: 0.4s;
}

.feature-item img {
  width: 80px;
}

.feature-item .title {
  margin: 20px 0 12px;
  font-weight: 600;
  font-size: 24px;
  line-height: 36px;
}

.feature-item .detail {
  font-size: 18px;
  line-height: 24px;
  color: #D1D1D1;
}

.fees {
  margin-top: 100px;
  margin-right: 100px;
  position: relative;
  background: url("../assets/features_bg.png") no-repeat;
  background-size: cover;
  padding: 40px var(--padding-section);
}

.fee-title {
  font-family: "Space Ranger";
  font-weight: 400;
  font-size: 120px;
  line-height: 120px;
}

.fee-list {
  margin-top: 20px;
}

.fee-item {
  display: flex;
  font-size: 24px;
  line-height: 36px;
  font-weight: 600;
  padding: 20px 4px;
  width: 640px;
}

.fee-item:not(:last-child) {
  border-bottom: 1px solid #FFFFFF66;
}

.fee-item > div:first-child {
  min-width: 160px;
}

.fee-item > div:last-child {
  margin-left: 20px;
  font-weight: 400;
  font-size: 18px;
  line-height: 28px;
  color: #D1D1D1;
}

.fee-image {
  position: absolute;
  bottom: -20px;
  right: -20px;
  width: calc(100% - 820px);
}

.fee-image img {
  width: 100%;
}

.fee-image:after {
  content: '';
  position: absolute;
  inset: 20px -20px -20px 20px;
  border: 1px solid var(--primary);
}

@media screen and (max-width: 600px) {
  .features-title {
    background: url("../assets/features_mb.png");
    background-size: cover;
    aspect-ratio: 375/100;
  }

  .features-title h1 {
    font-size: 28px;
    line-height: 36px;
  }

  .features-title div {
    display: none;
  }

  .feature-grid {
    display: block;
    padding: 0;
  }

  .feature-grid .feature-item {
    transition-delay: 0s;
  }

  .feature-item {
    padding: 40px;
  }

  .feature-item .title {
    font-size: 20px;
    line-height: 28px;
    margin: 12px 0 8px;
  }

  .feature-item .detail {
    font-size: 14px;
    line-height: 22px;
  }

  .fees {
    margin-right: 0;
    padding: 40px;
  }

  .fee-title {
    font-size: 110px;
    line-height: 65px;
  }

  .fee-title span {
    font-size: 36px;
    line-height: 30px;
  }

  .fee-item {
    width: 100%;
    display: block;
  }

  .fee-item > div:first-child {
    font-size: 20px;
    line-height: 28px;
  }

  .fee-item > div:last-child {
    margin-left: 0px;
    font-size: 14px;
    line-height: 22px;
  }

  .fee-image {
    display: none;
  }
}
</style>