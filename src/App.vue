<template>
  <div class="app-container">
    <LifePoints name="PaPa" :lifePoints="4000" :image="papaImg" />
    <LifePoints name="Ivan" :lifePoints="4000" :image="ivanImg" />
  </div>
</template>

<script>
import LifePoints from "./components/LifePoints.vue";

export default {
  name: "App",
  components: {
    LifePoints,
  },
  data() {
    return {
      ivanImg: require("./assets/imgs/beud.jpg"),
      papaImg: require("./assets/imgs/dhd.jpg"),
    };
  },
};
</script>

<style lang="less">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app-container {
  height: 100vh;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background: rgb(22, 101, 255);
  background: linear-gradient(
    0deg,
    rgba(22, 101, 255, 1) 0%,
    rgba(4, 34, 98, 1) 70%
  );
}
</style>
