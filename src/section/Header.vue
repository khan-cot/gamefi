<template>
  <div class="header">
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
    background: #171717;
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
</style>