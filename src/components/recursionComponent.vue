<template>
  <section class="recursion">
    <h2>{{ title }}</h2>

    <input
        type="number"
        class="input input_large"
        placeholder="write some number."
        v-model="inputValue"
    >

    <button @click.prevent="createArray(inputValue); summary(array)">add up to number</button>
    <div v-if="result">
      Summary with recursion: {{ result }}!
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Recursion'
    }
  },
  data() {
    return {
      inputValue: null,
      array: [],
      result: null
    }
  },
  methods: {
    createArray(number) {
      if (number === null) alert('write some number for created array')

      const min = 0
      const array = this.array
      array.length = 0

      while (min < number) {
        array.push(number--)
      }
    },
    summary(array, sum) {
      sum = sum || 0

      if (array.length) {
        return this.summary(array, sum + array.pop())
      } else {
        this.result = sum
      }
    }
  }
}
</script>