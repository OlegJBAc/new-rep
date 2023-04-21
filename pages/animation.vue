<template>
  <div class="animation">

    <div v-for="block in 5" class="animation__block"
         :class="`block-${block}`"
    >
      <h1>Block {{ block }}</h1>
    </div>

  </div>
</template>

<script>
import {gsap} from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
  name: "animation",
  mounted() {
    document.body.addEventListener('DOMContentLoaded', () => {
      gsap.to(".box", {
        scrollTrigger: ".block-3", // start the animation when ".box" enters the viewport (once)
        x: 500
      })
    })
  },

}
</script>

<style scoped>

</style>