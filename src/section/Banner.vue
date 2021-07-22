<template>
  <div class="banner">
    <div class="banner-background">
      <h1 class="banner-title">
        <div>Play, Trade & Farm</div>
        <div>Any Blockchain Game</div>
      </h1>
      <div class="banner-subtitle">
        GameFi is the all-encompassing hub for game finance. The platform services blockchain gamers, investors, and traders in one aggregator.
      </div>
      <div class="banner-btn primary" @click="scroll">Discover</div>
      <img alt id="xbox" src="../assets/xbox-controller.png"/>
      <img alt id="ps5" src="../assets/ps5-controller.png"/>
    </div>
    <div class="intro" id="parallax">
      <div class="intro-row">
        <div class="intro-item fade">
          <img alt src="../assets/rocket.svg"/>
          <div class="intro-item_title">For Game Projects</div>
          <ul class="intro-item_detail">
            <li>Raise fund in a healthy way </li>
            <li>Maintain community interest during game development</li>
            <li>Acquire early users</li>
          </ul>
        </div>
        <div class="intro-item fade">
          <img alt src="../assets/diamond.svg"/>
          <div class="intro-item_title">For Investors</div>
          <ul class="intro-item_detail">
            <li>Invest early in high quality</li>
            <li>Earning by staking, re-selling and renting out NFTs</li>
          </ul>
        </div>
        <div class="intro-item fade">
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
export default {
  name: "Banner",
  components: {},
  mounted() {
    function parallax() {
      let yScrollPosition = window.pageYOffset;
      const el = document.getElementById('parallax');
      el.style.bottom = (200 + yScrollPosition * 0.2) + 'px'
      const xbox = document.getElementById('xbox')
      xbox.style.transform = `rotate(${-yScrollPosition * 0.1}deg)`;
      const ps5 = document.getElementById('ps5')
      ps5.style.transform = `rotate(${yScrollPosition * 0.05}deg)`;
      requestAnimationFrame(parallax);
    }
    parallax();
  },
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
    position: relative;
  }

  .banner-background *:not(img) {
    position: relative;
    z-index: 1;
  }

  .banner-title {
    margin-top: 240px;
    font-family: "Space Ranger";
    font-size: 88px;
    line-height: 78px;
    text-align: center;
    width: 1100px;
  }

  .banner-title div:first-child {
    font-weight: 700;
  }

  .banner-title div:last-child {
    font-weight: 400;
  }

  .banner-subtitle {
    font-size: 22px;
    line-height: 32px;
    margin-top: 20px;
    text-align: center;
    width: 970px;
  }

  .banner-btn {
    background: #21361A;
    padding: 16px 80px;
    margin-top: 40px;
    cursor: pointer;
  }

  #xbox {
    position: absolute;
    top: 80px;
    left: 20px;
  }

  #ps5 {
    position: absolute;
    right: -160px;
    bottom: 200px;
  }

  .intro {
    position: absolute;
    bottom: 200px;
    left: 100px;
    right: 100px;
    transform: translateY(100%);
    background: #171717;
    padding: 80px;
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