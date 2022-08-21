<template>
  <div class="container">
    <LifePoints name="PaPa" :lifePoints="4000" />
    <LifePoints name="Ivan" :lifePoints="4000" />
  </div>
</template>

<script>
import LifePoints from "./components/LifePoints.vue";

export default {
  name: "App",
  components: {
    LifePoints,
  },
};
</script>

<style lang="less">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  height: 100vh;
  display: flex;
  justify-content: space-evenly;
}
</style>
