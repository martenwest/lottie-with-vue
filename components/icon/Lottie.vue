<template>
  <div
    ref="lavContainer"
    :style="{
      overflow: 'hidden',
    }"
  />
</template>

<script>
import lottie from 'lottie-web'

export default {
  props: {
    // This will be the icon json file
    json: {
      type: Object,
      required: true,
    },
  },

  mounted() {
    // When the component is mounted, lottie will do it's work creating a svg and renders the icon.
    this.anim = lottie.loadAnimation({
      container: this.$refs.lavContainer,
      renderer: 'svg',
      animationData: this.json,
    })
  },
}
</script>
