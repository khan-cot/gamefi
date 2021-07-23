<template>
  <div class="header" :style="{background: show ? '#0A0A0A' : '#171717'}">
    <a href="#">
      <img class="header-logo" src="../assets/logo.svg"/>
    </a>
    <ul class="header-link">
      <li class="header-link_item" v-for="(item, i) in items"
          @click="goTo(item)" :key="i">{{item}}</li>
      <li class="header-link_item">
        <a href="https://t.me/GameFi_Official" target="_blank" class="primary">Contact Us</a>
      </li>
    </ul>
    <div class="header-btn" @click="show = !show">
      <img v-if="show" alt src="../assets/close.svg"/>
      <img v-else alt src="../assets/menu.svg"/>
    </div>
    <div v-if="show" class="nav">
      <img alt class="xbox" src="../assets/xbox-controller.png"/>
      <img alt class="ps5" src="../assets/ps5-controller.png"/>
      <div class="link" v-for="(item, i) in items" @click="goAndClose(item)" :key="i">{{item}}</div>
      <div class="link">
        <a href="https://t.me/GameFi_Official" target="_blank">Contact Us</a>
      </div>
      <p>Follow</p>
      <div class="social">
        <a href="https://t.me/GameFi_Official" target="_blank" style="margin-right: 8px">
          <img alt src="../assets/tele_green.svg"/>
        </a>
        <a href="https://twitter.com/GameFi_Official" target="_blank">
          <img alt src="../assets/twitter_green.svg"/>
        </a>
      </div>
      <div style="flex: 1"></div>
      <div class="footer">© Icetea Labs, 2021</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      items: ['Features', 'Roadmap', 'Our Team'],
      show: false
    }
  },
  methods: {
    goTo(item) {
      const id = item.toLowerCase().replace(' ', '');
      const el = document.getElementById(id)
      el.scrollIntoView({behavior: 'smooth'})
    },
    goAndClose(item) {
      this.show = false;
      this.goTo(item)
    }
  }
}
</script>

<style scoped>
  .header {
    display: flex;
    position: fixed;
    z-index: 10;
    top: 0;
    left: 0;
    right: 0;
    padding: 24px var(--padding-section);
  }

  .header-logo {
    height: 24px;
    width: auto;
  }

  .header-link {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }

  .header-link_item {
    list-style-type: none;
    margin: 0 20px;
    font-size: 18px;
    line-height: 26px;
    color: white;
    cursor: pointer;
    white-space: nowrap;
  }

  .header-link_item a {
    text-decoration: none;
  }

  .header-btn {
    display: none;
    width: 60px;
    height: 60px;
    justify-content: center;
    align-items: center;
    background: var(--primary);
  }
  
  @media screen and (max-width: 600px) {
    .header {
      justify-content: space-between;
      padding: 0;
    }

    .header-logo {
      width: 115px;
      margin: 24px 32px 0;
    }

    .header-link {
      display: none;
    }

    .header-btn {
      display: flex;
    }

    .nav {
      position: fixed;
      top: 59px;
      left: 0;
      right: 0;
      bottom: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding-top: 60px;
      background: url("../assets/banner_mb.png");
      background-size: cover;
    }

    .link {
      font-weight: 700;
      font-size: 20px;
      line-height: 28px;
      margin-bottom: 20px;
    }

    .link a {
      text-decoration: none;
      color: white;
    }

    .nav p {
      margin-top: 40px;
      font-weight: 600;
      font-size: 14px;
      line-height: 24px;
    }

    .social {
      display: flex;
      align-items: center;
      margin-top: 8px;
    }

    .footer {
      display: flex;
      align-items: center;
      justify-content: center;
      border-top: 1px solid #FFFFFF25;
      padding: 24px;
      color: #C2C3D8;
      font-size: 14px;
      line-height: 24px;
    }

    .ps5 {
      position: absolute;
      bottom: -20px;
      right: -140px;
      transform: scale(0.7);
    }

    .xbox {
      position: absolute;
      top: -36px;
      left: -90px;
      transform: scale(0.3);
    }
  }
</style>