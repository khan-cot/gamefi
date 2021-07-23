<template>
  <div id="intro">
    <div class="intro">
      <img alt class="header" src="../assets/gamefi.png"/>
      <img alt class="header__mb" src="../assets/gamefi_mb.png"/>
      <div class="content">
        <img alt src="../assets/intro.png"/>
        <div class="detail fade">
          <h1>Game and Item <br/>Aggregator</h1>
          <p><span class="primary fw-700">Gamers</span> can access any blockchain’s games in one place, with tools to track their Play to Earn yields and
            item net values.</p>
          <p><span class="primary fw-700">Traders</span> can buy or sell yield-bear game items of any game, from any blockchain, on a single platform. </p>
        </div>
      </div>
    </div>
    <h1 class="title">
      <div>Dedicated Gaming</div>
      <div>Accelerator & Launchpad</div>
      <div class="subtitle">
        Gaming and crypto both recognize utility of digital assets and the value of scarcity. The boom in blockchain
        gaming was inevitable. GameFi is pioneering a framework for crypto games to advance their project delivery
        through pre-designed, ready-to-integrate smart contracts.
      </div>
    </h1>
    <div class="grid slide">
      <div class="item slideLeft">
        <img alt src="../assets/accelerator.svg"/>
        <div>Accelerator</div>
        <p>Developers and teams working on blockchain games can greatly accelerate their delivery target by adopting
          factory contracts for token economies, NFTs, and Play to Earn mechanics.</p>
      </div>
      <img alt src="../assets/image1.png" class="slideRight"/>
      <img alt src="../assets/image2.png" class="slideLeft delay"/>
      <div class="item slideRight delay">
        <img alt src="../assets/rocket.svg"/>
        <div>Launchpad</div>
        <p>Crypto games have earned recognition as some of the most profitable blockchain products. Gaming tokens are
          extremely desirable. GameFi is the first game-specific launchpad, with tools to facilitate the success of
          games.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Introduction"
}
</script>

<style scoped>
#intro {
  margin-top: 100px;
  padding-top: 100px;
}

.intro {
  position: relative;
}

.header,
.header__mb {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}

.header__mb {
  display: none;
}

.content {
  position: relative;
  z-index: 1;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 var(--padding-section);
}

.detail {
  max-width: 550px;
}

.detail h1 {
  font-weight: bold;
  font-size: 48px;
  line-height: 56px;
  margin-bottom: 32px;
}

.detail p {
  font-size: 18px;
  line-height: 24px;
  margin-bottom: 16px;
  color: #D1D1D1;
}

.title {
  background: url("../assets/gamefi.png") no-repeat;
  background-size: cover;
  aspect-ratio: 1440/231;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  margin-top: 80px;
  position: relative;
}

.subtitle {
  width: 1060px;
  font-size: 20px;
  line-height: 28px;
  font-weight: 400;
  color: #D1D1D1;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, 60px);
}

.grid {
  margin-top: 120px;
  padding: 0 var(--padding-section);
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.grid img {
  width: 100%;
}

.item {
  padding: 48px 60px;
  background: #0A0A0A;
}

.item img {
  width: 100px;
  margin-bottom: 20px;
}

.item div {
  font-weight: 700;
  font-size: 32px;
  line-height: 40px;
  margin-bottom: 12px;
}

.item p {
  font-size: 18px;
  line-height: 28px;
  color: #D1D1D1;
}

@media screen and (max-width: 600px) {
  .header {
    display: none;
  }

  .header__mb {
    display: block;
  }

  .content {
    flex-direction: column-reverse;
  }

  .detail h1 {
    font-size: 28px;
    line-height: 36px;
  }

  .detail p {
    font-size: 14px;
    line-height: 22px;
    margin-bottom: 32px;
  }

  .title {
    background: url("../assets/gamefi_mb.png") no-repeat;
    background-size: cover;
    aspect-ratio: 375/100;
    text-align: left;
    font-size: 28px;
    line-height: 36px;
  }

  .title div {
    width: 300px;
  }

  .subtitle {
    text-align: left;
    width: 300px;
    font-size: 14px;
    line-height: 22px;
    margin-top: 12px;
    position: static;
    transform: none;
  }

  .grid {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
    padding: 0;
    margin-top: 40px;
  }

  .grid img.slideLeft {
    order: 2;
  }

  .item {
    padding: 40px;
  }

  .item img {
    width: 48px;
    margin-bottom: 12px;
  }

  .item div {
    font-size: 20px;
    line-height: 28px;
    margin-bottom: 8px;
  }

  .item p {
    font-size: 14px;
    line-height: 22px;
  }
}
</style>