<template>
  <div id="app" class="main">
    <atropos :active-offset="40"
      :shadow-scale="1.15"
      :highlight="true"
      :always-active="true"
      :rotateXMax="45"
      :rotateYMax="45"
      :shadow="true"
      :shadow-offset="50"
      @enter="onEnter"
      @leave="onLeave"
      @rotate="onRotate">
      <div data-atropos-offset="-5" class="img_1 img">
        <div data-atropos-opacity="1;0.6" data-atropos-offset="-15" class="img_2 img"></div>
        <div data-atropos-opacity="1;0.6" data-atropos-offset="65" class="img_3 img"></div>
      </div>
      <!-- <div data-atropos-offset="0" class="img_2 img"></div>
      <div data-atropos-offset="5" class="img_3 img"></div> -->
    </atropos>
  </div>
</template>

<script setup>
import Atropos from 'atropos/vue';

const onEnter = () => console.log('Enter');
const onLeave = () => console.log('Leave');
const onRotate = (x, y) => console.log('Rotate', x, y);
</script>

<style scoped>
#app {
  padding: 0;
}
.main {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}
.my-atropos {
  width: 320px;
  height: 160px;
  position: relative;
}
.img {
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.img_1 {
  height: 90vh;
  width: 90vw;
  background-image: url('../assets/bg.jpg');
}
.img_2 {
  position: absolute;
  bottom: 10%;
  left: 10%;
  height: 20vh;
  width: 30vw;
  background-size: contain;
  background-image: url('../assets/dudes.png');
}
.img_3 {  
  position: absolute;
  bottom: 35%;
  left: 60%;
  height: 20vh;
  width: 20vw;
  background-size: contain;
  background-image: url('../assets/ball.png');
}
</style>
