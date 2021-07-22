<template>
  <div id="app">
    <Header/>
    <Banner/>
    <Introduction/>
    <Features/>
    <Token/>
    <Roadmap/>
    <Team/>
    <Partners/>
    <Subscribe/>
    <Footer/>
  </div>
</template>

<script>

import Header from "./section/Header";
import Banner from "./section/Banner";
import Features from "./section/Features";
import Roadmap from "./section/Roadmap";
import Partners from "./section/Partners";
import Team from "./section/Team";
import Subscribe from "./section/Subscribe";
import Footer from "./section/Footer";
import Introduction from "./section/Introduction";
import Token from "./section/Token";
export default {
  name: 'App',
  components: {
    Token,
    Introduction,
    Footer,
    Subscribe,
    Team,
    Partners,
    Roadmap,
    Features,
    Banner,
    Header
  },
  mounted() {
    const options = {
      root: null,
      rootMargin: '0px',
      threshold: 0.3
    }

    function addAnimation (entries) {
      entries.forEach((entry) => {
        if(entry.isIntersecting) {
          console.log(entry)
          entry.target.classList.add('active')
        }
      })
    }

    const observer = new IntersectionObserver(addAnimation, options);
    const fades = document.querySelectorAll('.fade')
    const slide = document.querySelectorAll('.slide')
    const sections = [...fades, ...slide]
    sections.forEach((section) => {
      observer.observe(section)
    })
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
