<template>
  <div>
    <canvas
      width="400"
      height="400"
      id="canvas"
      style="border: 1px solid #ccc"
    ></canvas>
    <button @click="addClickEvent">添加画布点击事件</button>
    <button @click="removeClickEvent">移除画布点击事件</button>
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

let canvas = null;

// 初始化画布
function init() {
  canvas = new fabric.Canvas("canvas");

  const rect = new fabric.Rect({
    top: 20,
    left: 20,
    width: 100,
    height: 50,
    fill: "#9896f1",
  });

  // 给矩形添加一个选中事件
  rect.on("selected", (options) => {
    console.log("选中矩形啦", options);
  });
  canvas.add(rect);

  addClickEvent();
}

// 移除画布点击事件
function removeClickEvent() {
  canvas.off("mouse:down");
}

// 添加画布点击事件
function addClickEvent() {
  removeClickEvent(); // 在添加事件之前先把该事件清除掉，以免重复添加
  canvas.on("mouse:down", (options) => {
    console.log(
      `x轴坐标: ${options.e.clientX};    y轴坐标: ${options.e.clientY}`
    );
  });
}

onMounted(() => {
  init();
});
</script>
