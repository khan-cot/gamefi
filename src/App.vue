<template>
  <div id="app">
    <Header/>
    <Banner/>
    <Features/>
    <Roadmap/>
    <Partners/>
    <Team/>
    <Subscribe/>
    <Footer/>
  </div>
</template>

<script>

import Header from "@/section/Header";
import Banner from "@/section/Banner";
import Features from "@/section/Features";
import Roadmap from "@/section/Roadmap";
import Partners from "@/section/Partners";
import Team from "@/section/Team";
import Subscribe from "@/section/Subscribe";
import Footer from "@/section/Footer";
export default {
  name: 'App',
  components: {
    Footer,
    Subscribe,
    Team,
    Partners,
    Roadmap,
    Features,
    Banner,
    Header
  }
}
</script>

<style>
@import "style/font/font.css";
@import 'style/style.css';

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
}
</style>
