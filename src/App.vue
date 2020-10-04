<template>
  <VueRain :rainSpeed="100" :rainFade="3000">
    <!-- Rendering water drop emoji using slots-->
    <div><p>&#128167;</p></div>
  </VueRain>
</template>

<script>
import VueRain from "./components/VueRain.vue";

export default {
  name: "App",
  components: {
    VueRain,
  },
};
</script>