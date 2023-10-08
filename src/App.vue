<template>
  <canvas
    width="200"
    height="200"
    id="canvas"
    style="border: 1px solid #ccc"
  ></canvas>
</template>

<script setup>
import { onMounted } from "vue";
import { fabric } from "fabric";

function init() {
  const canvas = new fabric.Canvas("canvas");

  // 圆形
  const circle = new fabric.Circle({
    radius: 30,
    fill: "#f55",
    top: 70,
    left: 70,
  });

  circle.hasBorders = circle.hasControls = false;

  canvas.add(circle);

  function animate(e, dir) {
    if (e.target) {
      // fabric.util.animate({
      //   startValue: e.target.get("angle"),
      //   endValue: e.target.get("angle") + (dir ? 10 : -10),
      //   duration: 100,
      // });
      fabric.util.animate({
        startValue: e.target.get("scaleX"),
        endValue: e.target.get("scaleX") + (dir ? 0.2 : -0.2),
        duration: 100,
        onChange: function (value) {
          e.target.scale(value);
          canvas.renderAll();
        },
        onComplete: function () {
          e.target.setCoords();
        },
      });
    }
  }
  canvas.on("mouse:down", function (e) {
    animate(e, 1);
  });
  canvas.on("mouse:up", function (e) {
    animate(e, 0);
  });
}

onMounted(() => {
  init();
});
</script>
