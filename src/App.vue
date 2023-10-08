<template>
  <div>
    <canvas
      id="canvas"
      width="400"
      height="400"
      style="border: 1px solid #ccc"
    ></canvas>
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  // 初始化画布
  const canvas = new fabric.Canvas("canvas");

  // 矩形（参照物）
  const rect = new fabric.Rect({
    top: 10,
    left: 10,
    width: 40,
    height: 40,
    fill: "orange",
  });

  // 圆形（参照物）
  const circle = new fabric.Circle({
    top: 30,
    left: 30,
    radius: 50,
    fill: "green",
  });
  canvas.add(rect, circle); // 将矩形和圆形添加到画布中

  // 监听鼠标滚轮事件
  canvas.on("mouse:wheel", (opt) => {
    let delta = opt.e.deltaY; // 滚轮向上滚一下是 -100，向下滚一下是 100
    let zoom = canvas.getZoom(); // 获取画布当前缩放值

    // 控制缩放范围在 0.01~20 的区间内
    zoom *= 0.999 ** delta;
    if (zoom > 20) zoom = 20;
    if (zoom < 0.01) zoom = 0.01;

    // 设置画布缩放比例
    canvas.setZoom(zoom);
  });
}

onMounted(() => {
  init();
});
</script>
