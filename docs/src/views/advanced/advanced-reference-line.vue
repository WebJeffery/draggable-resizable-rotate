// #region all
// #region template
<template>
  <div class="view-box">
    <div id="toolbar">Alignment helper lines</div>
    <div class="container">
      <VueDragResizeRotate
        :w="200"
        :h="200"
        :parent="true"
        :debug="false"
        :min-width="200"
        :min-height="200"
        :isConflictCheck="true"
        :snap="true"
        :snapTolerance="10"
        @refLineParams="getRefLineParams"
        style="background-color: rgb(174, 213, 129)"
      ></VueDragResizeRotate>
      <VueDragResizeRotate
        :w="200"
        :h="200"
        :parent="true"
        :x="210"
        :debug="false"
        :min-width="200"
        :min-height="200"
        :isConflictCheck="true"
        :snap="true"
        :snapTolerance="10"
        @refLineParams="getRefLineParams"
        style="background-color: rgb(129, 212, 250)"
      ></VueDragResizeRotate>
      <VueDragResizeRotate
        :w="200"
        :h="200"
        :parent="true"
        :x="420"
        :debug="false"
        :min-width="200"
        :min-height="200"
        :isConflictCheck="true"
        :snap="true"
        :snapTolerance="10"
        @refLineParams="getRefLineParams"
        style="background-color: rgb(239, 154, 154)"
      ></VueDragResizeRotate>
      <span
        class="ref-line v-line"
        v-for="(item, index) in vLine"
        :key="'v_' + index"
        v-show="item.display"
        :style="{
          left: item.position,
          top: item.origin,
          height: item.lineLength
        }"
      />
      <span
        class="ref-line h-line"
        v-for="(item, index) in hLine"
        :key="'h_' + index"
        :style="{
          top: item.position,
          left: item.origin,
          width: item.lineLength
        }"
      />
    </div>
  </div>
</template>
// #endregion template

// #region script
<script>
export default {
  data() {
    return {
      vLine: [],
      hLine: []
    };
  },
  methods: {
    getRefLineParams(params) {
      const { vLine, hLine } = params;
      this.vLine = vLine;
      this.hLine = hLine;
    }
  }
};
</script>
// # endregion script

// # region style
<style scoped>
.ref-line {
  position: absolute;
  background-color: rgb(219, 89, 110);
  z-index: 9999;
}
.v-line {
  width: 1px;
}
.h-line {
  height: 1px;
}
</style>
// #endregion style
// #endregion all