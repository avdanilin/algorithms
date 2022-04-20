<template>
  <section class="binary-search">
    <h2 class="title">{{ title }}</h2>

    <input
        class="input"
        type="number"
        :placeholder="`Write some number from range ${from} to ${to}`"
        v-model="inputValue"
    >
    <button @keydown.enter="binarySearch" @click="binarySearch">
      Поиск по массиву
    </button>
    <div v-if="result">
      {{ result }}
    </div>
  </section>
</template>

<script>
export default {
  name: 'BinarySearch',
  props: {
    title: {
      type: String,
      default: 'Binary search'
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
  data() {
    return {
      inputValue: 0,
      array: [],
      result: null
    }
  },
  methods: {
    createArray() {
      this.array.length = 0

      let low = this.from
      const high = this.to

      while (low <= high) {
        this.array.push(low++)
      }
    },
    binarySearch: function () {
      this.createArray()
      this.result = 'whimper :('

      const that = this
      const list = this.array
      let low = list[0]
      let high = list.length - 1
      let value = this.inputValue
      while (low <= high) {
        const middle = Math.floor((low + high) / 2)
        const guess = list[middle]

        if (guess === value) {
          that.result = `There is a breakthrough - ${guess}!`
        }

        if (guess < value) {
          low = middle + 1
        } else {
          high = middle - 1
        }
      }

      return this.result
    }
  }
}
</script>
