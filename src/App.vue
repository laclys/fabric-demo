<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric"; // 引入 fabric

function init() {
  const canvas = new fabric.Canvas("c"); // 这里传入的是canvas的id

  // 创建一个长方形
  const rect = new fabric.Rect({
    top: 30, // 距离容器顶部 30px
    left: 30, // 距离容器左侧 30px
    width: 100, // 宽 100px
    height: 60, // 高 60px
    fill: "red", // 填充 红色
  });

  // 在canvas画布中加入矩形（rect）。add是“添加”的意思
  canvas.add(rect);
}

// 需要在页面容器加载完才能开始初始化（页面加载完才找到 canvas 元素）
// onMounted 是 Vue3 提供的一个页面生命周期函数：实例被挂载后调用。
// onMounted 官方文档说明：https://v3.cn.vuejs.org/guide/composition-api-lifecycle-hooks.html
onMounted(() => {
  init(); // 执行初始化函数
});
</script>

<template>
  <div>
    <canvas
      width="400"
      height="400"
      id="c"
      style="border: 1px solid #ccc"
    ></canvas>
  </div>
</template>

<style scoped>
</style>
