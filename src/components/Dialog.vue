<template>
  <div class="dialog-wrapper">
    <div v-show="value" class="overlay" @click="close"></div>
    <transition name="fade">
      <div v-show="value" class="main" ref="main">
        <img class="close" alt src="../assets/close2.svg" @click="close"/>
        <img class="right" alt src="../assets/arrow_right.svg" @click="next"/>
        <img class="left" alt src="../assets/arrow_left.svg" @click="prev"/>
        <div class="image">
          <img alt :src="image"/>
        </div>
        <div class="content">
          <div class="header">
            <h4 class="title">{{name}}</h4>
            <div class="subtitle">{{title}}</div>
          </div>
          <div class="detail">
            <p v-for="(desc, i) in descriptions" :key="i">{{desc}}</p>
          </div>
          <div class="link">
            <a v-for="(link, i) in links" target="_blank" :key="i" :href="link.href">
              <img alt :src="link.img"/>
            </a>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>


export default {
  name: "Dialog",
  props: {
    value: Boolean,
    data: Object
  },
  computed: {
    image() {
      return 'members/' + this.data?.image[window.innerWidth < 600 ? 1 : 0] || 'thi.png'
    },
    name() {
      return this.data?.name || ''
    },
    title() {
      return this.data?.title || ''
    },
    links() {
      return this.data?.links || []
    },
    descriptions() {
      return this.data?.descriptions || []
    }
  },
  watch: {
    value(v) {
      document.querySelector('body').style.overflow =  (v ? 'hidden' : '')
      if(!v && this.$refs && this.$refs.main) {
        this.$refs.main.scrollTop = 0
      }
    }
  },
  methods: {
    close() {
      this.$emit('input', false)
    },
    next() {
      this.$emit('next')
    },
    prev() {
      this.$emit('prev')
    }
  }
}
</script>

<style scoped>
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.42);
    z-index: 18;
  }

  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
  }

  .fade-enter, .fade-leave-to {
    opacity: 0;
  }

  .main {
    position: fixed;
    z-index: 20;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: #1C1C1E;
    padding: 60px 80px;
    border-radius: 20px;
    display: flex;
    align-items: flex-start;
    width: 1080px;
  }

  .close {
    position: absolute;
    top: 20px;
    right: 20px;
    cursor: pointer;
    z-index: 2;
  }

  .right,
  .left {
    position: absolute;
    top: 50%;
    cursor: pointer;
    transform: translateY(-50%);
    z-index: 2;
  }

  .right {
    right: 20px;
  }

  .left {
    left: 20px;
  }

  .image {
    margin-right: 80px;
    min-width: 300px;
    position: relative;
  }

  .image img {
    width: 100%;
  }

  .content {
    font-weight: 300;
    font-size: 16px;
    line-height: 26px;
  }

  .header {
    margin-top: 12px;
  }

  .title {
    font-weight: 600;
    font-size: 32px;
    line-height: 40px;
  }

  .subtitle {
    margin: 4px 0;
    font-weight: 600;
    font-size: 20px;
    line-height: 28px;
    color: var(--primary);
  }

  .link {
    display: flex;
    align-items: center;
    margin-top: 40px;
  }

  .link a {
    margin-right: 8px;
  }

  .detail p{
    margin: 12px 0;
    font-size: 18px;
    line-height: 28px;
    color: #D1D1D1;
  }

  @media screen and (max-width: 600px) {
    .main {
      flex-direction: column;
      width: calc(100% - 24px);
      align-items: center;
      max-height: calc(100% - 24px);
      overflow: scroll;
      padding: 24px;
      background: #303030;
    }

    .image {
      margin-right: 0;
      margin-bottom: 20px;
    }

    h4.title {
      text-align: left;
    }
  }
</style>