<template>
  <div class="view-box">
    <div id="toolbar">
      <p :style="style">
        I turn red when
        <i>onResizeStart</i>
        is called. Callback then prevents resizing.
      </p>
    </div>
    <div class="container">
      <VueDragResizeRotate :on-resize-start="onResizeStart"></VueDragResizeRotate>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      style: {
        color: "black"
      }
    };
  },
  methods: {
    onResizeStart(e) {
      console.log(e)
      this.style.color = "red";
      return false;
    }
  }
};
</script>
