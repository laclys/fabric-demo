<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";
import jailCellBars from "./assets/jail_cell_bars.png"; // 引入背景图

function init() {
  const canvas = new fabric.Canvas("canvas");
  // 圆
  let circle = new fabric.Circle({
    left: 100,
    top: 100,
    radius: 50,
  });

  /*   // 线性渐变
  let gradient = new fabric.Gradient({
    type: "linear", // linear or radial
    gradientUnits: "pixels", // pixels or pencentage 像素 或者 百分比
    coords: { x1: 0, y1: 0, x2: circle.width, y2: 0 }, // 至少2个坐标对（x1，y1和x2，y2）将定义渐变在对象上的扩展方式
    colorStops: [
      // 定义渐变颜色的数组
      { offset: 0, color: "red" },
      { offset: 0.2, color: "orange" },
      { offset: 0.4, color: "yellow" },
      { offset: 0.6, color: "green" },
      { offset: 0.8, color: "blue" },
      { offset: 1, color: "purple" },
    ],
  }); */
  /* 径向渐变 */
  let gradient = new fabric.Gradient({
    type: "radial",
    coords: {
      r1: 50, // 该属性仅径向渐变可用，外圆半径
      r2: 0, // 该属性仅径向渐变可用，外圆半径
      x1: 50, // 焦点的x坐标
      y1: 50, // 焦点的y坐标
      x2: 50, // 中心点的x坐标
      y2: 50, // 中心点的y坐标
    },
    colorStops: [
      { offset: 0, color: "#fee140" },
      { offset: 1, color: "#fa709a" },
    ],
  });

  circle.set("fill", gradient);
  canvas.add(circle);
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
