<template>
  <div class="rain">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "VueRain",
  props: {
    rainSpeed: {
      type: Number,
      default: 30,
    },
    rainFade: {
      type: Number,
      default: 5000,
    },
  },
  data() {
    return {
      refreshRate: null,
      fade: null,
    };
  },
  mounted() {
    this.initData();
    setInterval(this.createRain, this.rainSpeed);
  },
  methods: {
    initData() {
      if (this.$props.rainSpeed) {
        this.refreshRate = this.rainSpeed;
      }
      if (this.$props.rainFade) {
        this.fade = this.rainFade;
      }
    },
    createRain() {
      // Using vanilla JS for DOM operations
      const rain = document.createElement("div");
      rain.classList.add("rain");

      rain.style.left = Math.random() * 100 + "vw";
      rain.style.animationDuration = Math.random() * 2 + 3 + "s";

      rain.innerText = this.$slots.default[0].elm.innerText;
      document.body.appendChild(rain);

      // Fade away time set
      setTimeout(() => {
        rain.remove();
      }, this.fade);
    },
  },
};
</script>

<style>
/* CSS animation class */
.rain {
  position: fixed;
  top: -1vh;
  font-size: 2rem;
  transform: translateY(0);
  animation: fall 3s linear forwards;
}

@keyframes fall {
  to {
    transform: translateY(105vh);
  }
}
</style>