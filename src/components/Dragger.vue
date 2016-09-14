<template lang="html">
  <img draggable="false" src="../assets/map.jpg" alt="" id="map"/>
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
  let top = viewport.height() - map.height()
  let left = viewport.width() - map.width()
  return [top, 0, 0, left]
}

function onCreate() {
  $(document).ready( () => {
    const $map = $('#map')
    const $viewport = $(window)
    let constrainTo = boundaryCalc($map, $viewport)

    $map.on('load', () => {
      $map.pep({ constrainTo, useCSSTranslation: false })
    })
  })
}

</script>

<style lang="css">
</style>
