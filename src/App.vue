<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";
import jailCellBars from "./assets/jail_cell_bars.png"; // 引入背景图

function init() {
  const canvas = new fabric.Canvas("canvas");
  /* 圆形 */
/*   const circle = new fabric.Circle({
    top: 100,
    left: 100,
    radius: 50, // 圆的半径 50
    fill: 'green'
  })
  canvas.add(circle) */

  /* 三角形 */
  /*   const triangle = new fabric.Triangle({
    top: 100,
    left: 100,
    width: 80, // 底边长度
    height: 100, // 底边到对角的距离
    fill: 'blue'
  })
  canvas.add(triangle) */

  /* 折线 */
  /*   const polyline = new fabric.Polyline(
    [
      { x: 30, y: 30 },
      { x: 150, y: 140 },
      { x: 240, y: 150 },
      { x: 100, y: 30 },
    ],
    {
      fill: "transparent", // 如果画折线，需要填充透明
      stroke: "#6639a6", // 线段颜色：紫色
      strokeWidth: 5, // 线段粗细 5
    }
  );
  canvas.add(polyline); */
  /* 多边形 */
  /*   const polygon = new fabric.Polygon([
    {x: 30, y: 30},
    {x: 150, y: 140},
    {x: 240, y: 150},
    {x: 100, y: 30}
  ], {
    fill: '#ffd3b6', // 填充色
    stroke: '#6639a6', // 线段颜色：紫色
    strokeWidth: 5 // 线段粗细 5
  })
  canvas.add(polygon) */
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
