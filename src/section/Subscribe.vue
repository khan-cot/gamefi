<template>
  <div class="subscribe">
    <h3 class="title">Get the latest in<br/>your inbox</h3>
    <div class="input-wrapper">
      <input type="email" placeholder="Enter your email" v-model="email"/>
      <div class="btn" @click.stop="sendEmail">
        <span>Subscribe</span>
      </div>
    </div>
    <div :class="`message ${message.ok ? 'success' : 'error'}`">{{ message.info }}</div>
    <div class="social">
      <a href="https://t.me/GameFi_Official" target="_blank">
        <img alt src="../assets/tele_black.svg"/>
      </a>
      <a href="https://twitter.com/GameFi_Official" target="_blank">
        <img alt src="../assets/twitter_black.svg"/>
      </a>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "Subscribe",
  data() {
    return {
      email: '',
      message: {
        ok: false,
        info: ''
      }
    }
  },
  methods: {
    sendEmail() {
      const url = 'https://icetea.us3.list-manage.com/subscribe/post-json?u=0fbb6304481fc398e41b28f09&id=5968f8dfbe&c=?'
      axios.post(url, {email: this.email})
          .then(() => {
            this.message = {
              ok: true,
              info: 'Thank you for subscribing!'
            };
            setTimeout(() => {
              this.message = {
                ok: false,
                info: ''
              }
            }, 3000)
          })
          .catch((e) => {
            console.error(e)
            this.message = {
              ok: false,
              info: 'Something wrong was happened. Please try again later!'
            };
            setTimeout(() => {
              this.message = {
                ok: false,
                info: ''
              }
            }, 3000)
          })
    }
  }
}
</script>

<style scoped>
.subscribe {
  background-color: var(--primary);
  background-image: url("../assets/subscribe.png");
  background-size: cover;
  position: relative;
  padding: 80px 0 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

h3.title {
  font-family: "Space Ranger";
  font-size: 72px;
  line-height: 60px;
  color: #0A0A0A;
  margin-bottom: 27px;
  text-align: center;
}

.input-wrapper {
  display: flex;
  align-items: center;
  width: 560px;
}

input {
  flex: 1;
  background: white;
  font-size: 16px;
  line-height: 28px;
  padding: 14px 0 14px 20px;
  color: #0A0A0A;
  border: none;
  outline: none;
}

.btn {
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary);
  font-weight: 700;
  font-size: 20px;
  line-height: 28px;
  padding: 14px 40px;
  background: #0A0A0A;
  cursor: pointer;
}

.message {
  margin-top: 12px;
  font-style: italic;
}

.success {
  color: white;
}

.error {
  color: #ff4452
}

.social {
  display: flex;
  align-items: center;
  justify-content: center;
}

.social a {
  margin: 8px;
}

@media screen and (max-width: 600px) {
  .subscribe {
    flex-direction: column;
    width: 100%;
    padding: 60px 24px;
    background-image: url("../assets/subscribe_mb.png");
    background-repeat: no-repeat;
    background-size: contain;
  }

  .subscribe > img {
    margin-left: 0;
    margin-bottom: 12px;
    width: 120px;
  }

  h3.title {
    font-size: 52px;
    line-height: 38px;
  }

  .input-wrapper {
    flex-direction: column;
    background: transparent;
    align-items: stretch;
    box-shadow: none;
    width: 100%;
  }

  input {
    margin-bottom: 8px;
  }

  .social {
    display: none;
  }
}
</style>