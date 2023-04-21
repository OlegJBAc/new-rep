<template>
  <div class="page-main">
    <div class="content">
      <h1 class="page-title">Main page</h1>
      <p>Blabla<b>bla</b>bla</p>
    </div>

    <div id="aura"></div>
  </div>
</template>

<script>

const mouseTrackCoordinate = (isStartTrack) => {
  const pageMain = document.querySelector('.page-main')
  const pageTitle = document.querySelector('.page-title')

  const aura = document.querySelector('#aura')

  aura.style.position = 'absolute'
  const trackMouse = (e) => {
    e.stopPropagation()
    const rect = e.currentTarget.getBoundingClientRect()

    const y = e.clientY - rect.top
    const x = e.clientX - rect.left

    aura.style.top = `${y - 100}px`
    aura.style.left = `${x - 100}px`

  }

  if(isStartTrack) {
    pageMain.addEventListener('mousemove', trackMouse)
  }else {
    pageMain.removeEventListener('mousemove', trackMouse)
  }

}

export default {
  name: "main",
  mounted() {
    mouseTrackCoordinate(true)
  },
  unmounted() {
    mouseTrackCoordinate(false)
  },
  methods: {

  },
}

</script>

