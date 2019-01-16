<template>
  <div id="slider" class="slider" @mousemove="mouseMoving">
    <div class="slider-cards">
      <div
        v-for="(slide, index) in slides"
        :key="index"
        class="slider-card"
        @mousedown="startDrag"
        @mouseup="stopDrag"
      >
        <img :src="slide.image" :alt="slide.title" draggable="false">
      </div>
    </div>
    <div class="slider-info">
      <h1>{{selectedSlide.title}}</h1>
      <p>{{selectedSlide.description}}</p>
      <button class="slider-button">BOOK</button>
    </div>
  </div>
</template>

<script>
export default {
  el: '#slider',
  name: 'Slider',
  props: {
    msg: String,
  },
  data: function data() {
    return {
      slides: [
        {
          title: 'Ready Player One',
          description:
            'When the creator of a popular video game system dies, a virtual contest is created to compete for his fortune.',
          image: 'https://image.tmdb.org/t/p/w300_and_h450_bestv2/pU1ULUq8D3iRxl1fdX2lZIzdHuI.jpg',
        },
        {
          title: 'Avengers: Infinity War',
          description:
            'As the Avengers and their allies have continued to protect the world from threats too large for any...',
          image: 'https://image.tmdb.org/t/p/w300_and_h450_bestv2/7WsyChQLEftFiDOVTGkv3hFpyyt.jpg',
        },
        {
          title: 'Coco',
          description:
            'Despite his family’s baffling generations-old ban on music, Miguel dreams of becoming an accomplished musician...',
          image: 'https://image.tmdb.org/t/p/w300_and_h450_bestv2/eKi8dIrr8voobbaGzDpe8w0PVbC.jpg',
        },
      ],
      selectedIndex: 0,
    };
  },
  computed: {
    selectedSlide() {
      return this.slides[this.selectedIndex];
    },
  },
  methods: {
    startDrag(e) {},
    stopDrag() {},
    mouseMoving(e) {},
  },
};
</script>

<style>
.slider {
  overflow: hidden;
  background-color: #1f1140;
  width: 360px;
  height: 640px;
}
.slider-cards {
  position: relative;
  width: 900px;
  margin: 20px 50px;
  z-index: 1;
}
.slider-card {
  display: inline-block;
  background-color: grey;
  overflow: hidden;
  width: 260px;
  height: 360px;
  margin-right: 30px;
  border-radius: 12px;
  box-shadow: 0px 60px 20px -20px rgba(0, 0, 0, 0.3);
}
.slider-info {
  position: relative;
  overflow: hidden;
  background-color: white;
  margin-top: -200px;
  margin-left: 30px;
  padding: 200px 20px 0;
  width: 260px;
  height: 200px;
  text-align: center;
  border-radius: 8px;
}
.slider-info h1 {
  font-family: Arial Black, Gadget, sans-serif;
  line-height: 25px;
  font-size: 23px;
}
.slider-info p {
  font-family: Arial, Helvetica, sans-serif;
}
.slider-button {
  position: absolute;
  width: 100%;
  height: 50px;
  bottom: 0;
  left: 0;
  border: none;
  color: white;
  background-color: #e71284;
  font-size: 18px;
  font-family: Arial, Helvetica, sans-serif;
}
</style>