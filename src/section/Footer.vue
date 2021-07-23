<template>
  <div class="wrapper">
    <div class="info">
      <div>
        <img class="logo" alt="logo" src="../assets/logo.svg"/>
        <div>
          From the labs behind Red Kite launchpad <br/>and several NFT games
        </div>
        <div class="social">
          <a href="https://t.me/GameFi_Official" target="_blank" style="margin-right: 8px">
            <img alt src="../assets/tele_green.svg"/>
          </a>
          <a href="https://twitter.com/GameFi_Official" target="_blank">
            <img alt src="../assets/twitter_green.svg"/>
          </a>
        </div>
      </div>
      <div class="column">
        <h2 class="title">Our Team</h2>
        <div v-for="(item, i) in scrolls" :key="i" @click="goTo(item, 'scroll')">
          {{item}}
        </div>
      </div>
      <div class="column">
        <h2 class="title">Token</h2>
        <div v-for="(item, i) in tokens" :key="i" @click="goTo(item.link, 'file')">
          {{item.title}}
        </div>
      </div>
      <div class="column">
        <h2 class="title">FAQ</h2>
        <div v-for="(item, i) in faqs" :key="i" @click="goTo(item, 'open')">
          {{item.title}}
        </div>
      </div>
    </div>
    <div class="footer">© Icetea Labs, 2021</div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      scrolls: ['Features', 'Roadmap', 'Our Team'],
      tokens: [
        { title: 'Token Metrics', link: ''},
        { title: 'Token Utilities', link: ''},
      ],
      faqs: [
        { title: 'Terms and Conditions', link: ''},
        { title: 'Whitepaper', link: ''},
        { title: 'Contact Us', link: ''},
        { title: 'FAQ', link: ''},
      ]
    }
  },
  methods: {
    goTo(item, mode) {
      if(mode === 'scroll') {
        const id = item.toLowerCase().replace(' ', '');
        const el = document.getElementById(id)
        el.scrollIntoView({behavior: 'smooth'})
      } else if (mode === 'open') {
        window.open(item.link, '_blank')
      } else if (mode === 'file') {
        const url = require(item.link)
        const link = document.createElement('a')
        link.setAttribute('download', item.title)
        link.setAttribute('href', url)
        link.click()
      }
    }
  }
}
</script>

<style scoped>
  .wrapper {
    background: #0A0A0A;
    font-size: 18px;
    line-height: 28px;
  }

  .info {
    display: flex;
    padding: var(--padding-article) var(--padding-section) 80px;
  }

  .info > div:first-child {
    flex: 1;
  }

  .logo {
    margin-bottom: 36px;
  }

  .column {
    flex: 0 1 200px;
  }

  .column:not(:last-child) {
    padding-right: 40px;
  }

  .title {
    font-weight: bold;
    font-size: 20px;
    line-height: 26px;
    margin-top: 24px;
    margin-bottom: 24px;
  }

  .column > div {
    line-height: 40px;
    cursor: pointer;
  }

  .social {
    display: flex;
    align-items: center;
    margin-top: 32px;
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

  @media screen and (max-width: 600px) {
    .info {
      flex-wrap: wrap;
    }

    .info > div:first-child {
      flex: 0 0 100%;
      padding: 40px 12px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border-bottom: 1px solid #FFF4;
    }

    .info > div:first-child div {
      text-align: center;
    }

    .info > div:first-child br {
      display: none;
    }

    .column {
      text-align: center;
      flex: 0 0 50%;
      padding-right: 0;
    }

    .column > div {
      font-size: 16px;
      line-height: 32px;
    }
  }
</style>