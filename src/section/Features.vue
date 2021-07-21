<template>
  <div id="features">
    <div class="section">
      <h1 class="title">Features</h1>
      <div class="list">
        <div class="item">
          <div>Game NFT Sales</div>
        </div>
        <div class="item">
          <div>Game Token Sales</div>
        </div>
        <div class="item">
          <div>Farming and NFT Renting</div>
        </div>
        <div class="item">
          <div>Cross-game marketplace</div>
        </div>
        <div class="item">
          <div>Minigames</div>
        </div>
        <div class="item">
          <div>DAO Governance</div>
        </div>
      </div>
      <div class="image">
        <img alt src="../assets/features_img.png"/>
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
    margin-top: 400px;
    padding-top: 100px;
  }

  .section {
    margin-top: 100px;
    margin-right: 100px;
    position: relative;
    background: url("../assets/features_bg.png") no-repeat;
    background-size: cover;
    padding: 24px var(--padding-section);
  }

  h1.title {
    font-family: "Space Ranger";
    font-weight: 400;
    font-size: 200px;
    line-height: 200px;
  }

  .list {
    margin-top: 20px;
  }

  .item {
    display: flex;
    align-items: center;
    font-size: 28px;
    line-height: 36px;
    font-weight: 700;
    margin-bottom: 20px;
  }

  .item:before {
    content: '';
    min-width: 10px;
    height: 10px;
    background: #FFFFFF;
    margin-right: 12px;
  }

  .image {
    position: absolute;
    bottom: -20px;
    right: -20px;
  }

  .image:after {
    content: '';
    position: absolute;
    inset: 20px -20px -20px 20px;
    border: 1px solid var(--primary);
  }

</style>