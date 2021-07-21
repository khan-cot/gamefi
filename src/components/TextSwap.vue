<template>
  <svg>
    <text text-anchor="middle"
          x="50%" y="90%"
          fill="none"
          stroke="white"
          stroke-width="2px"
          stroke-dasharray="1000"
          stroke-dashoffset="0"
          font-size="90px"
          font-family="Space Ranger"
    >{{text}}</text>
  </svg>
</template>

<script>
export default {
  name: "TextSwap",
  data() {
    return {
      texts: ['Launchpad', 'Finance', 'Hub'],
      text: 'Launchpad',
      index: 2
    }
  },
  mounted() {
    setTimeout(() => {
      this.text = 'Finance';
      setInterval(() => {
        this.text = this.texts[this.index % 3];
        this.index++;
      }, 10000)
    }, 8000)
  }
}
</script>

<style scoped>
  svg {
    width: 540px;
    height: 52px;
  }

  svg text {
    animation: dashOffset 10s ease-in infinite;
  }

  @keyframes dashOffset {
    0% {
      stroke-dashoffset: 0;
    }
    80% {
      stroke-dashoffset: 1200;
    }
  }
</style>