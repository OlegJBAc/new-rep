<template>
  <ul class="nav-menu">
    <li>
      <NuxtLink to="/main">
        <span>Main</span>
      </NuxtLink>
    </li>
    <li>
      <NuxtLink to="/test">
        <span>Test</span>
      </NuxtLink>
    </li>
    <li>
      <NuxtLink to="/animation">
        <span>Animation</span>
      </NuxtLink>
    </li>
  </ul>
</template>

<script>
export default {
  name: "navMenu"
}
</script>

<style scoped>

</style>