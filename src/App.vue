<template>
  <canvas
    width="200"
    height="200"
    id="canvas"
    style="border: 1px solid #ccc"
  ></canvas>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  const canvas = new fabric.Canvas("canvas");

  // 圆形
  const circle = new fabric.Circle({
    radius: 30,
    fill: "#f55",
    top: 70,
    left: 70,
  });

  canvas.hoverCursor = "wait"; // 设置等待指针

  canvas.add(circle);
}

onMounted(() => {
  init();
});
</script>
