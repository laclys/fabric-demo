<template>
  <canvas
    width="400"
    height="400"
    id="canvas"
    style="border: 1px solid #ccc"
  ></canvas>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  const canvas = new fabric.Canvas("canvas");

  const rect = new fabric.Rect({
    top: 100,
    left: 100,
    width: 200,
    height: 100,
    fill: "red",
  });

  // 元素禁止选中
  rect.selectable = false;

  canvas.add(rect);
}

onMounted(() => {
  init();
});
</script>
