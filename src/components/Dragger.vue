<template lang="html">
  <img draggable="false" src="../assets/map.jpg" alt="" class="map"/>
</template>

<script>
import $ from 'jquery'
import pep from 'jquery.pep'

export default {
  data() {
    return {
    };
  },
  created: onCreate,
  computed: {},
  ready() {},
  attached() {},
  methods: {},
  components: {}
}

function boundaryCalc(map, viewport) {
  const top = viewport.height() - map.height()
  const left = viewport.width() - map.width()
  return [top, 0, 0, left]
}

function onCreate() {
  $(document).ready( () => {
    const $map = $('.map')
    const $viewport = $(window)
    const constrainTo = boundaryCalc($map, $viewport)

    $map.on('load', () => {
      $map.pep({ constrainTo })
    })
  })
}

</script>

<style lang="css">
</style>
