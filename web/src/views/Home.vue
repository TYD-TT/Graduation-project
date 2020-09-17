<template>
  <div id="home">
    <div>
      <b-carousel
        fade
        id="carousel-1"
        v-model="slide"
        :interval="2000"
        controls
        indicators
        img-height="80%"
        style="text-shadow: 1px 1px 2px #333;"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
        <b-carousel-slide
          v-for="(item,key) in imgs"
          :key="key"
          :img-src="item.path"
        ></b-carousel-slide>
      </b-carousel>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 0,
      sliding: null,
      imgs: [
        {
          id: 1,
          path: "http://localhost/img/one.jpg",
        },
        {
          id: 2,
          path: "http://localhost/img/two.jpg",
        },
        {
          id: 3,
          path: "http://localhost/img/three.jpg",
        },
      ],
    };
  },
  methods: {
    onSlideStart() {
      this.sliding = true;
    },
    onSlideEnd() {
      this.sliding = false;
    },
  },
};
</script>
<style lang="scss">
</style>