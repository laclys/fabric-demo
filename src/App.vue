<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";
import jailCellBars from "./assets/jail_cell_bars.png"; // 引入背景图

function init() {
  const canvas = new fabric.Canvas("canvas");
  const text = new fabric.IText("Bilibili");
  canvas.add(text);
}
/* 使用 new fabric.IText 可以创建可编辑文本，用法和 new fabric.Text 一样。

IText 比 Text 多了个大写 “I” 在首字母上。 */

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
