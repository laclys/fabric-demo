<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";
import jailCellBars from "./assets/jail_cell_bars.png"; // 引入背景图

function init() {
  const canvas = new fabric.Canvas("canvas");
  const text = new fabric.Text("Bilibili");
  canvas.add(text);
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
      id="canvas"
      style="border: 1px solid #ccc"
    ></canvas>
  </div>
</template>

<style scoped>
</style>
