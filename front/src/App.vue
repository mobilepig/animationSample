<template>
  <div class="container">
    <div
      class="anibox inTag animate__animated animate__bounce animate__infinite infinite"
    ></div>
    <!-- 재반복 횟수 -->
    <div
      class="anibox animate__animated animate__bounce animate__repeat-2"
    ></div>
    <div class="anibox box1"></div>
    <div class="anibox box2"></div>
    <div class="anibox box3"></div>
    <!-- 무한pulse -->
    <div
      class="anibox box4 animate__pulse animate__animated animate__infinite infinite"
    ></div>
    <div class="anibox box5 tossing"></div>
    <div class="anibox box6"></div>
    <div class="anibox box7"></div>
    <div class="anibox box8"></div>
    <div class="anibox inCSS"></div>
  </div>
</template>

<script>
import { reactive } from "vue";
import axios from "axios";

// ref
// http://www.justinaguilar.com/animations/index.html#
// https://animate.style/

export default {
  setup() {
    const data = reactive({
      test: "test data",
    });

    const axiosTest = () =>
      axios.get("/api/test").then((res) => {
        alert(res.data);
      });

    return {
      data,
      axiosTest,
    };
  },
};
</script>

<style lang="scss">
#app {
}
body {
  margin: 0;
}

.container {
  display: flex;
  flex-direction: column;
  .anibox {
    width: 100px;
    height: 100px;
    margin: 10px;
    border-radius: 5px;
    background-color: yellow;
  }

  // duration 꼭해주래!!
  .inCSS {
    animation: bounceIn;
    animation-duration: 1s;
  }

  .box1 {
    animation: zoomInDown;
    animation-duration: 1s;
  }
  .box2 {
    animation: zoomInUp;
    animation-duration: 1s;
  }
  .box3 {
    animation: slideInLeft;
    animation-duration: 0.5s;
  }
  .box4 {
    background-color: red;
  }
  .box5 {
    background-color: blue;
  }
  .box1 {
    animation: zoomInDown;
    animation-duration: 1s;
  }
  .box1 {
    animation: zoomInDown;
    animation-duration: 1s;
  }
}
</style>
