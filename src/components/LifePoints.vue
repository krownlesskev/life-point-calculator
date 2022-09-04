<template>
  <div class="container">
    <div class="name">
      <h1>{{ name }}</h1>
    </div>
    <div class="lifepoints">
      <h2 v-if="currentLifePoints > 0">Life Points: {{ currentLifePoints }}</h2>
      <p v-else>{{ name }} has no more life points</p>
    </div>
    <div class="image-container"><img :src="image" :alt="image" /></div>
    <div class="buttons-container">
      <div class="buttons-top">
        <button
          class="buttons success"
          @click="inc50"
          :disabled="currentLifePoints <= 0"
        >
          +50
        </button>
        <button
          class="buttons success"
          @click="inc100"
          :disabled="currentLifePoints <= 0"
        >
          +100
        </button>
        <button
          class="buttons success"
          @click="inc1000"
          :disabled="currentLifePoints <= 0"
        >
          +1000
        </button>
      </div>
      <div class="buttons-bottom">
        <button
          class="buttons danger"
          @click="dec50"
          :disabled="currentLifePoints <= 0"
        >
          -50
        </button>
        <button
          class="buttons danger"
          @click="dec100"
          :disabled="currentLifePoints <= 0"
        >
          -100
        </button>
        <button
          class="buttons danger"
          @click="dec1000"
          :disabled="currentLifePoints <= 0"
        >
          -1000
        </button>
      </div>
    </div>
    <div v-if="currentLifePoints <= 0">
      <button class="buttons" @click="reset">RESET</button>
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
    playerName: String,
    image: String,
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
  width: 340px;
  color: #000;
  background-color: #ce9233;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 6px solid #000;
  border-radius: 20px 20px;
  &:hover {
    transform: scale(1.05);
  }

  .name {
    margin: 8px 0;
    padding: 4px;
    width: 90%;
    border-radius: 4px;
    box-shadow: 3px 3px 8px, -3px -1px 4px #fff;
  }

  .lifepoints {
    width: 80%;
    text-align: right;
    font-size: 0.9em;
    margin: 4px;
  }

  .image-container {
    display: flex;
    border: 4px solid #000;
    border-radius: 8px;
    margin-bottom: 8px;
    width: 90%;
    box-shadow: 0 0 10px;
    img {
      border: none;
      border-radius: 4px;
      width: 100%;
    }
  }

  .buttons-container {
    background-color: #debe6a;
    border: 4px solid #c06530;
    height: 110px;
    width: 90%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;

    .buttons {
      margin: 4px;
      border: none;
      width: 75px;
      height: 30px;
      transition: 0.3s;
      font-size: 18px;
      font-weight: bold;
      &:hover {
        cursor: pointer;
        transform: scale(1.1);
        border: 1px solid #000;
      }

      &.success {
        border-radius: 10px 10px 4px 4px;
        background: rgb(217, 249, 214);
        background: linear-gradient(
          0deg,
          rgba(217, 249, 214, 1) 14%,
          rgba(6, 255, 0, 1) 100%
        );
      }
      &.danger {
        border-radius: 4px 4px 10px 10px;
        background: rgb(255, 0, 0);
        background: linear-gradient(
          0deg,
          rgba(255, 0, 0, 1) 15%,
          rgba(255, 255, 255, 1) 100%
        );
      }
      &:active {
        transition: 0s;
        background: #fff;
        transform: scale(1.2);
      }
    }
  }
}
</style>
