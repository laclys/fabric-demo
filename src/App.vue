<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric"; // 引入 fabric

function init() {
  const canvas = new fabric.Canvas("c"); // 这里传入的是canvas的id

  // 这个就是可交互的canvas

  // 创建一个长方形
  const rect = new fabric.Rect({
    top: 100, // 距离容器顶部 100px
    left: 100, // 距离容器左侧 100px
    width: 30, // 矩形宽度 30px
    height: 30, // 矩形高度 30px
    fill: "red", // 填充 红色
  });

  // 在canvas画布中加入矩形（rect）。add是“添加”的意思
  canvas.add(rect);
}

onMounted(() => {
  init(); // 执行初始化函数
});
</script>

<template>
  <div>
    <canvas
      width="400"
      height="400"
      id="c"
      style="border: 1px solid #ccc"
    ></canvas>
  </div>
</template>

<style scoped>
</style>
