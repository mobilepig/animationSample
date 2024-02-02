<template>
  <div class="container">
    <div class="box_1">
      <div
        class="anibox inTag animate__animated animate__bounce animate__infinite infinite"
      ></div>
      <!-- 재반복 횟수 -->
      <div
        class="anibox animate__animated animate__bounce animate__repeat-2"
      ></div>
      <!-- 무한pulse -->
      <div
        class="anibox box4 animate__pulse animate__animated animate__infinite infinite"
      ></div>
      <div class="anibox box5 tossing"></div>
      <div class="tossing">
        <div
          class="anibox boxDual animate__pulse animate__animated animate__infinite infinite"
        ></div>
      </div>
    </div>
    <div class="box_2">
      <div class="anibox slideDown">slideDown</div>
      <div class="anibox slideUp">slideUp</div>
      <div class="anibox slideLeft">slideLeft</div>
      <div class="anibox slideRight">slideRight</div>
      <div class="anibox slideExpandUp">slideExpandUp</div>
      <div class="anibox expandUp">expandUp</div>
    </div>
    <div class="box_3">
      <div class="anibox fadeIn">fadeIn</div>
      <div class="anibox expandOpen">expandOpen</div>
      <div class="anibox bigEntrance">bigEntrance</div>
      <div class="anibox hatch">hatch</div>
      <div class="anibox bounce">bounce</div>
      <div class="anibox pulse">pulse</div>
    </div>
    <div class="box_4">
      <div class="anibox floating">floating</div>
      <div class="anibox tossing">tossing</div>
      <div class="anibox pullUp">pullUp</div>
      <div class="anibox pullDown">pullDown</div>
      <div class="anibox stretchLeft">stretchLeft</div>
      <div class="anibox stretchRight">stretchRight</div>
    </div>
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
  .anibox {
    width: 120px;
    height: 100px;
    margin: 10px;
    border-radius: 5px;
    background-color: yellow;
    display: flex;
    justify-content: center;
    align-items: center;
    border: red 1px solid;
  }

  display: flex;
  .box_1 {
    width: 25%;

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
    .boxDual {
      background-color: green;
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
  .box_2 {
    width: 25%;
  }
  .box_3 {
    width: 25%;
  }
  .box_4 {
    width: 25%;
  }
}
</style>
