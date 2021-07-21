<template>
  <div class="banner">
    <div class="banner-background">
      <h1 class="banner-title">
        <p style="margin-bottom: 4px">The first game</p>
        <TextSwap/>
        <p>on Polygon</p>
      </h1>
      <div class="banner-btn primary" @click="scroll">Discover</div>
    </div>
    <div class="intro" id="intro">
      <div class="intro-title">
        <div>Play, Trade & Farm</div>
        <div>Any Blockchain Game</div>
      </div>
      <div class="intro-subtitle">
        GameFi is the all-encompassing hub for game finance. The platform services blockchain gamers, investors, and traders in one aggregator.
      </div>
      <div class="intro-row">
        <div class="intro-item">
          <img alt src="../assets/rocket.svg"/>
          <div class="intro-item_title">For Game Projects</div>
          <ul class="intro-item_detail">
            <li>Raise fund in a healthy way </li>
            <li>Maintain community interest during game development</li>
            <li>Acquire early users</li>
          </ul>
        </div>
        <div class="intro-item">
          <img alt src="../assets/diamond.svg"/>
          <div class="intro-item_title">For Investors</div>
          <ul class="intro-item_detail">
            <li>Invest early in high quality</li>
            <li>Earning by staking, re-selling and renting out NFTs</li>
          </ul>
        </div>
        <div class="intro-item">
          <img alt src="../assets/gamepad.svg"/>
          <div class="intro-item_title">For Game Players</div>
          <ul class="intro-item_detail">
            <li>Exchange NFTs</li>
            <li>Rent NFTs</li>
            <li>Pay others to stake tokens to power-up your game heroes</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TextSwap from "@/components/TextSwap";
export default {
  name: "Banner",
  components: {TextSwap},
  methods: {
    scroll() {
      const el = document.getElementById('intro')
      el.scrollIntoView({behavior: 'smooth'})
    }
  }
}
</script>

<style scoped>
  .banner {
    position: relative;
  }

  .banner-background {
    aspect-ratio: 1440 / 980;
    background: url("../assets/banner.png") no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h1.banner-title {
    margin-top: 240px;
    font-family: "Space Ranger";
    font-weight: 700;
    font-size: 90px;
    line-height: 80px;
    text-align: center;
  }

  .banner-btn {
    background: #21361A;
    padding: 16px 80px;
    margin-top: 40px;
    cursor: pointer;
  }

  .intro {
    position: absolute;
    bottom: 0;
    left: 100px;
    right: 100px;
    transform: translateY(50%);
    background: #171717;
    padding: 60px;
  }

  .intro-title {
    font-size: 60px;
    line-height: 52px;
    font-weight: 700;
  }

  .intro-subtitle {
    font-size: 22px;
    line-height: 32px;
    color: #D1D1D1;
    margin-top: 20px;
    margin-bottom: 40px;
  }

  .intro-row {
    display: flex;
  }

  .intro-item {
    flex: 1 1 auto;
    padding-right: 40px;
  }

  .intro-item_title {
    font-size: 24px;
    line-height: 32px;
    margin-bottom: 12px;
  }

  .intro-item_detail {
    font-size: 18px;
    line-height: 28px;
    color: #D1D1D1;
    margin-bottom: 8px;
    list-style: none;
  }

  .intro-item_detail li {
    display: flex;
  }

  .intro-item_detail li:before {
    content: '';
    min-width: 5px;
    height: 5px;
    background: var(--primary);
    margin-top: 12px;
    margin-right: 12px;
  }
</style>