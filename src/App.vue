<template>
  <div class="full-width center-content">
    <HelloWorld name="towrabbit" />
    <img
      src="../static/img/headIcon.png"
      alt=""
      class="icon"
    >
    <div>
      <canvas id="map" />
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import * as drawMap from './js/drawMap.js'
export default {
  components: {
    HelloWorld
  },
  mounted: () => {
    const mapCanvas = document.getElementById('map')
    if (mapCanvas) {
      mapCanvas.width = window.innerWidth
      mapCanvas.height = window.innerHeight
      let img = new Image()
      img.src = 'http://towrabbit.oss-cn-beijing.aliyuncs.com/images/iconHeart.png'
      img.onload = function () {
        const context = mapCanvas.getContext('2d')
        // context.drawImage(img, 0, 0, 100, 100, 0, 0, 100, 100)
      }
    }
  }
}
console.log(drawMap.add(1, 2))
drawMap.newCanvas('map')
let img = new Image()
img.src = 'http://towrabbit.oss-cn-beijing.aliyuncs.com/images/iconHeart.png'
img.onload = function () {
  console.log('nyan')
  console.log(img)
  drawMap.drawATile(img, 0, 0, 100, 100, 0, 0, 100, 100)
}
</script>

<style lang="scss" scoped>
  .icon{
    width:150px;height:150px;
    display:block;
    margin:0 auto;
    border-radius:50%;
    border:1px solid #ccc;
    background-color: #fff;
  }
  #map{
    background-color: #ffffff;
  }
  body{
    width:100%;
    height:100%;
    position:absolute;
  }
</style>
