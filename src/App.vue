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

  canvas.add(circle);
  canvas.selection = false; // 允许从画布框选，但允许选中元素。
}

onMounted(() => {
  init();
});
</script>
