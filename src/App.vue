<template>
  <div>
    <canvas
      width="400"
      height="400"
      id="canvas"
      style="border: 1px solid #ccc"
    ></canvas>
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

// 初始化
function init() {
  const canvas = new fabric.Canvas("canvas");

  const rect = new fabric.Rect({
    left: 100,
    top: 100,
    width: 100,
    height: 100,
    fill: "red",
  });

  // 设置矩形动画
  /*   第一个参数是要设置动画的属性。

第二个参数是动画的结束值。

第三个参数是一个对象 */
  rect.animate("angle", "+=360", { // "+=360"相对动画 
    onChange: canvas.renderAll.bind(canvas), // 每次刷新的时候都会执行
    duration: 2000, // ms 默认500ms
    easing: fabric.util.ease.easeOutBounce, // 缓冲效果
  });

  canvas.add(rect);
}

onMounted(() => {
  init();
});
</script>
