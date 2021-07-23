<template>
  <div class="section" id="roadmap">
    <h1 class="title">Roadmap</h1>
    <div class="map">
      <div class="item fade">
        <div class="time">Q3 2021</div>
        <div class="divider"></div>
        <div class="info">IDO on GameFi, DAO Maker, Red Kite</div>
      </div>
      <div class="item fade">
        <div class="time">Q3 2021</div>
        <div class="divider"></div>
        <div class="info">Launch token sales <br/>and NFT sales modules</div>
      </div>
      <div class="item fade">
        <div class="time">Q4 2021</div>
        <div class="divider right"></div>
        <div class="info">Launch marketplace and staking</div>
      </div>
      <div class="item fade">
        <div class="time">Q4 2021</div>
        <div class="divider left"></div>
        <div class="info">Launch NFT renting</div>
      </div>
      <div class="item fade">
        <div class="time">Q1 2022</div>
        <div class="divider"></div>
        <div class="info">Minigames, initial DAO</div>
      </div>
      <div class="item fade">
        <div class="time">Q2 2022</div>
        <div class="divider"></div>
        <div class="info">More mature DAO</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Roadmap"
}
</script>

<style scoped>
  .section {
    margin-top: 100px;
    padding-top: 100px;
    background: #0A0A0A;
  }

  h1.title {
    background: url("../assets/roadmap.png");
    background-size: cover;
    aspect-ratio: 1440/231;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    font-size: 32px;
    line-height: 40px;
    text-transform: uppercase;
  }

  .map {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 100px 0;
    padding: 24px var(--padding-section) var(--padding-section);
  }

  .item:nth-child(3n) {
    transition-delay: 0.4s;
  }

  .item:nth-child(3n+2) {
    transition-delay: 0.2s;
  }

  .time {
    color: var(--primary);
    font-weight: bold;
    font-size: 20px;
    line-height: 28px;
  }

  .divider {
    width: 100%;
    height: 16px;
    margin: 12px 0 30px;
    position: relative;
  }

  .divider:after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    width: 6px;
    background: var(--primary);
  }

  .divider:before {
    content: '';
    position: absolute;
    top: 6px;
    height: 4px;
    left: 0;
    right: 0;
    background: url("../assets/dot_arr.png");
    background-size: cover;
  }

  .right:before {
    right: -160px;
  }

  .left:before {
    left: -160px;
  }

  .info {
    font-weight: bold;
    font-size: 24px;
    line-height: 36px;
    padding-right: 60px;
  }

  @media screen and (max-width: 600px) {
    h1.title {
      background: url("../assets/roadmap_mb.png");
      background-size: cover;
      aspect-ratio: 375/100;
      font-size: 28px;
      line-height: 36px;
      text-transform: none;
    }

    .map {
      display: block;
    }

    .item {
      position: relative;
      padding: 0 60px 60px;
    }

    .time {
      margin-bottom: 8px;
      font-size: 16px;
      line-height: 28px;
    }

    .divider {
      position: absolute;
      top: 9px;
      left: 12px;
      margin: 0;
      height: 100%;
      width: 16px;
    }

    .divider:before {
      top: 0;
      left: 6px;
      right: unset;
      height: 100%;
      width: 4px;
      background: url("../assets/dotted_mb.png");
      background-size: cover;
    }

    .divider:after {
      top: 0;
      right: 0;
      bottom: unset;
      height: 6px;
      width: auto;
    }

    .info {
      padding: 0;
      font-size: 16px;
      line-height: 28px;
    }
  }
</style>