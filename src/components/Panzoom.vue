<template>
  <div class="panzoom-container">
    <p>Hold Shift To Zoom</p>
    <div class="panzoom-element" ref="panzoom-element">
      <slot ref="panzoom-element"></slot>
    </div>
  </div>
</template>

<script>
import Panzoom from '@panzoom/panzoom';

export default {
  name: "Panzoom",
  data() {
    return {
      panzoom: null
    }
  },
  mounted() {
    const elem = this.$refs['panzoom-element'];

    if (elem) {
      this.panzoom = Panzoom(elem, {maxScale: 2, origin: '50% 50%'});
      elem.parentElement.addEventListener('wheel', (event) => {
        if (!event.shiftKey) {
          return
        }
        this.panzoom.zoomWithWheel(event)
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.panzoom-container {
  width: 100%;
  height: 100%; // probably want to set a real height here
  min-height: 600px;
  border: 1px solid #000000;
}

.panzoom-element {
  display: inline-block;
}
</style>