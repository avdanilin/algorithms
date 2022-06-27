<template>
  <section class="maximum-number">
    <h2 class="title">{{ title }}</h2>

    <button @click="getMaximumNumber">Get maximum number from random array</button>

    <div v-if="randomArray">
      Random array - {{ randomArray }}
    </div>

    <div v-if="maximumNumber">
      Maximum number from array - {{ maximumNumber }}
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Maximum number'
    },
    from: {
      type: Number,
      default: 0
    },
    to: {
      type: Number,
      default: 50
    }
  },
  data: () => ({
    randomArray: null,
    maximumNumber: null
  }),
  methods: {
    getMaximumNumber() {
      this.maximumNumber = null;
      this.randomArray = this.generateRandomArray(0, 100);

      if (!this.randomArray) return false;

      for (let i = 0; i < this.randomArray.length; i++) {
        if (this.randomArray[i] > this.maximumNumber) {
          this.maximumNumber = this.randomArray[i];
        }
      }
    },
    generateRandomArray(min, max) {
      const randomArray = [];
      const randomMaxNumber = Math.floor(Math.random() * (max - min + 1) + min);

      for (let j = min; j < randomMaxNumber; j++) {
        randomArray.push(j)
      }

      return randomArray;
    }
  }
}
</script>

<style scoped>

</style>