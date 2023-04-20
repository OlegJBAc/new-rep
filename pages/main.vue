<template>
  <div class="page-main">
    <h1>Main page</h1>
    <div id="cursor"></div>
    <div id="aura"></div>
  </div>
</template>

<script>

const mouseTrackCoordinate = (isStartTrack) => {
  const body = document.querySelector('body')
  body.addEventListener('mousemove', e => {
    let clientX = e.pageX,
        clientY = e.pageY
  })
  const cursor = document.getElementById('cursor'),
      follower = document.getElementById('aura'),
      links = document.getElementById('a')

  let mouseX = 0,
      mouseY = 0,
      posX = 0,
      posY = 0

  function mouseCoords(e) {
    mouseX = e.pageX
    mouseY = e.pageY
  }
  gsap.to({}, .01, {
    repeat: -1,
    onRepeat: () => {
      posX += (mouseX - posX) / 5
      posY += (mouseY - posY) / 5

      gsap.set(follower, {
        css: {
          left: posX - 23,
          top: posY - 23
        }
      })

    }
  })
}

export default {
  name: "main",
  mounted() {
    mouseTrackCoordinate(true)
  },
  unmounted() {
    // mouseTrackCoordinate(false)
  },
  methods: {},
}

</script>

