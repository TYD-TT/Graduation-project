<template>
  <div>
    <div>
      <div>
        <b-navbar toggleable="lg" type="dark" variant="info">
          <b-navbar-brand href="#">首页</b-navbar-brand>
          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
              <b-nav-item href="#">一一一</b-nav-item>
              <b-nav-item href="#">二二二</b-nav-item>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
              <b-nav-form>
                <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
              </b-nav-form>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
      </div>
    </div>
    <div>
      <b-carousel
        id="carousel-1"
        v-model="slide"
        :interval="4000"
        controls
        indicators
        img-height="360"
        background="#ababab"
        style="text-shadow: 1px 1px 2px #333;height:360px"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
      >
        <!-- Text slides with image -->
        <b-carousel-slide style="height:360px" img-src="https://s1.ax1x.com/2020/09/14/wrmtsA.jpg"></b-carousel-slide>
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
.img-fluid {
  height: 100%;
}
</style>
