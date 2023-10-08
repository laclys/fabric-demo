<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";
import jailCellBars from "./assets/jail_cell_bars.png"; // 引入背景图

function init() {
  const canvas = new fabric.Canvas("canvas");
  const textbox = new fabric.Textbox("this is textbox", {
    width: 250,
  });
  canvas.add(textbox);
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
