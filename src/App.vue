<template>
  <div>
    <canvas
      id="canvas"
      width="200"
      height="200"
      style="border: 1px solid #ccc"
    ></canvas>
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  // 初始化画布
  const canvas = new fabric.Canvas("canvas", {
    backgroundColor: "#a5dee5",
  });

  const rect = new fabric.Rect({
    left: 50,
    top: 50,
    height: 20,
    width: 20,
    fill: "green",
  });

  const circle = new fabric.Circle({
    left: 80,
    top: 80,
    radius: 40,
    fill: "red",
  });

  canvas.add(rect, circle);
  console.log("toSVG", canvas.toSVG()); // 输出 SVG
  console.log("toPng", canvas.toDataURL("png")); // 在控制台输出 png（base64）

  // 使用 canvas.toDataURL('png') 可以输出 png 图片。但这个操作可能会打断 canvas 的渲染，所以之后要再执行以下 canvas.requestRenderAll()
  
  canvas.requestRenderAll();

  console.log("canvas stringify ", JSON.stringify(canvas));
  console.log("canvas toJSON", canvas.toJSON());
  console.log("canvas toObject", canvas.toObject());
}

onMounted(() => {
  init();
});
</script>
