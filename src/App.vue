<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric"; // 引入 fabric

function init() {
  const canvas = new fabric.Canvas("canvas", {
    width: 300, // 画布宽度
    height: 300, // 画布高度
    backgroundColor: "#eee", // 画布背景色
  });

  // 圆形
  const circle = new fabric.Circle({
    radius: 30, // 圆的半径
    top: 20, // 距离容器顶部 20px
    left: 20, // 距离容器左侧 20px
    fill: "pink", // 填充 粉色
  });

  canvas.add(circle); // 将圆形添加到 canvas 画布里
}

onMounted(() => {
  init();
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
