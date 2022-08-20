<template>
  <div class="container">
    <div class="lp">
      <h1>{{ name }}</h1>
      <h2 v-if="currentLifePoints > 0">Life Points: {{ currentLifePoints }}</h2>
      <p v-else>{{ name }} has no more life points</p>
      <div>
        <button class="buttons" @click="dec1000">-1000</button>
        <button class="buttons" @click="dec100">-100</button>
        <button class="buttons" @click="dec50">-50</button>
        <button class="buttons" @click="inc50">+50</button>
        <button class="buttons" @click="inc100">+100</button>
        <button class="buttons" @click="inc1000">+1000</button>
      </div>
      <div v-if="currentLifePoints <= 0">
        <button class="buttons" @click="reset">RESET</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LifePoints",
  data() {
    return {
      currentLifePoints: this.lifePoints,
    };
  },
  props: {
    name: String,
    lifePoints: Number,
  },
  methods: {
    inc1000() {
      this.currentLifePoints += 1000;
    },
    inc100() {
      this.currentLifePoints += 100;
    },
    inc50() {
      this.currentLifePoints += 50;
    },
    dec50() {
      this.currentLifePoints -= 50;
    },
    dec100() {
      this.currentLifePoints -= 100;
    },
    dec1000() {
      this.currentLifePoints -= 1000;
    },

    reset() {
      this.currentLifePoints = 4000;
    },
  },
};
</script>

<style lang="less" scoped>
.container {
  height: 100vh;
  display: flex;
  justify-content: space-evenly;
  align-items: center;

  .lp {
    border: 4px solid red;
    border-radius: 10px;
    width: 400px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;

    .buttons {
      margin: 4px;
    }
  }
}
</style>
