// #region all
// #region template
<template>
  <div class="view-box">
    <div id="toolbar">允许内部元素拖拽</div>
    <div class="container">
      <VueDragResizeRotate :enable-native-drag="false" :x="0" :y="0" :w="200" :h="200">
        <p>Do not allow browser-native JavaScript drag-and-drop</p>
        <p>Native drag disabled. Try to drag the component from the ball.</p>
        <img src="@assets/ball.svg" />
      </VueDragResizeRotate>
      <VueDragResizeRotate :enable-native-drag="true" :x="0" :y="200" :w="200" :h="200">
        <p>Allow browser-native JavaScript drag and drop</p>
        <p>Native drag enabled. Try to drag the component from the ball.</p>
        <img src="@assets/ball.svg" />
      </VueDragResizeRotate>
    </div>
  </div>
</template>
// #endregion template
// #endregion all