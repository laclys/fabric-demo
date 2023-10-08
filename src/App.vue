<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";
import jailCellBars from "./assets/jail_cell_bars.png"; // 引入背景图

function init() {
  const canvas = new fabric.Canvas("canvas");
  const circle = new fabric.Circle({
    top: 100,
    left: 100,
    radius: 50, // 半径：50px
    backgroundColor: "green", // 背景色：绿色
    fill: "orange", // 填充色：橙色
    stroke: "#f6416c", // 边框颜色：粉色
    strokeWidth: 5, // 边框粗细：5px
    strokeDashArray: [20, 5, 14], // 边框虚线规则：填充20px 空5px 填充14px 空20px 填充5px ……
    shadow: "10px 20px 6px rgba(10, 20, 30, 0.4)", // 投影：向右偏移10px，向下偏移20px，羽化6px，投影颜色及透明度
    transparentCorners: true, // 选中时，角是被填充了。true 空心；false 实心
    borderColor: "#16f1fc", // 选中时，边框颜色：天蓝
    borderScaleFactor: 5, // 选中时，边的粗细：5px
    borderDashArray: [20, 5, 10, 7], // 选中时，虚线边的规则
    cornerColor: "#a1de93", // 选中时，角的颜色是 青色
    cornerStrokeColor: "pink", // 选中时，角的边框的颜色是 粉色
    cornerStyle: "circle", // 选中时，叫的属性。默认rect 矩形；circle 圆形
    cornerSize: 20, // 选中时，角的大小为20
    cornerDashArray: [10, 2, 6], // 选中时，虚线角的规则
    selectionBackgroundColor: "#7f1300", // 选中时，选框的背景色：朱红
    padding: 40, // 选中时，选择框离元素的内边距：40px
    borderOpacityWhenMoving: 0.6, // 当对象活动和移动时，对象控制边界的不透明度
  });

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
