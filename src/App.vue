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

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  const canvas = new fabric.Canvas("canvas");

  // 椭圆
  const ellipse = new fabric.Ellipse({
    top: 20,
    left: 20,
    rx: 100,
    ry: 50,
    fill: "#ddd",
    originX: "center", // 旋转x轴：left, right, center
    originY: "center", // 旋转y轴：top, bottom, center
  });

  // 文本
  const text = new fabric.Text("Hello World", {
    top: 20,
    left: 20,
    fontSize: 20,
    originX: "center",
    originY: "center",
  });

  // 建组
  const group = new fabric.Group([ellipse, text], {
    top: 50, // 整组距离顶部100
    left: 100, // 整组距离左侧100
    angle: -10, // 整组旋转-10deg
  });

  canvas.add(group);
}

onMounted(() => {
  init();
});
</script>
