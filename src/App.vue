<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  const canvas = new fabric.Canvas("canvas");

  // // 设置背景图
  // // 参数1：背景图资源（可以引入本地，也可以使用网络图）
  // // 参数2：设置完背景图执行以下重新渲染canvas的操作，这样背景图就会展示出来了
  // canvas.setBackgroundImage("/src/assets/pic.jpg", canvas.renderAll.bind(canvas), {
  //   // angle: 15, // 旋转背景图
  // });
  fabric.Image.fromURL("/src/assets/pic.jpg", (img) => {
    // 设置背景图
    canvas.setBackgroundImage(img, canvas.renderAll.bind(canvas), {
      scaleX: canvas.width / img.width, // 计算出图片要拉伸的宽度
      scaleY: canvas.height / img.height, // 计算出图片要拉伸的高度
    });
  });
}
// 使用了 fabric.Image.fromURL 这个 api 来加载图片，第一个参数是图片地址，第二个参数是回调函数。


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
