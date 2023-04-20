<template>
  <div class="app">
    <NavMenu/>
    <NuxtPage/>
  </div>
</template>

<script>

import {defineComponent} from "vue";
import NavMenu from "~/components/navMenu.vue";

export default defineComponent({
  components: {
    NavMenu
  },
})
</script>

<style lang="scss">
@import "styles/app.scss";
</style>