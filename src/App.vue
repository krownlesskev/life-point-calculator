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

<style>
.container {
  display: flex;
  justify-content: space-evenly;
}
</style>
