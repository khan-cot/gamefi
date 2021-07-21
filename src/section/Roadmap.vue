<template>
  <div class="section" id="roadmap">
    <h1 class="title">Roadmap</h1>
    <div class="map">
      <div class="item">
        <div class="time">15 August</div>
        <div class="divider"></div>
        <div class="info">IDO on GameFi, DAO Maker, Red Kite</div>
      </div>
      <div class="item">
        <div class="time">2nd half August</div>
        <div class="divider"></div>
        <div class="info">Launch token sales <br/>and NFT sales modules</div>
      </div>
      <div class="item">
        <div class="time">September</div>
        <div class="divider"></div>
        <div class="info">Launch marketplace and staking</div>
      </div>
      <div class="item">
        <div class="time">Q4 2021</div>
        <div class="divider"></div>
        <div class="info">Launch NFT renting</div>
      </div>
      <div class="item">
        <div class="time">Q1 2022</div>
        <div class="divider"></div>
        <div class="info">Minigames, initial DAO</div>
      </div>
      <div class="item">
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
    margin-top: 200px;
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
    grid-gap: 100px 60px;
    padding: 24px var(--padding-section) var(--padding-section);
    background: #171717;
  }

  .time {
    color: var(--primary);
    font-weight: bold;
    font-size: 20px;
    line-height: 28px;
  }

  .divider {
    width: 6px;
    height: 16px;
    background: var(--primary);
    margin: 12px 0 30px;
  }

  .info {
    font-weight: bold;
    font-size: 24px;
    line-height: 36px;
  }
</style>