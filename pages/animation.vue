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

gsap.registerPlugin(ScrollTrigger)

export default {
  name: "animation",
  mounted() {
    gsap.to('.block-3', {
      scrollTrigger: '.block-3',
      background: 'black',
      y: -200,
      duration: 2,
    })

  },
}

</script>