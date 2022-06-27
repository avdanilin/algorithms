<template>
  <section class="qsort">
    <h2>{{ title }}</h2>

    <input
        type="number"
        class="input input_large"
        placeholder="write some number for create array"
        v-model="inputValue"
    >

    <button @click.prevent="quickSort(array); createArray(inputValue);">Create array and sort this</button>
    <div v-if="result.length">
      Sorted with quick sort! <br> {{ result }}!
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Quick sort'
    }
  },
  data() {
    return {
      inputValue: null,
      array: [],
      result: []
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
    quickSort(array) {
      this.array.length = 0

      if (array.length < 2) {
        this.result = array
        return array
      } else {
        const pivot = Math.floor(Math.random() * array.length)
        const less = array.filter(value => value < pivot)
        const greater = array.filter(value => value > pivot)
        this.result = [...this.quickSort(less), pivot, this.quickSort(greater)]

        return  [...this.quickSort(less), pivot, this.quickSort(greater)]
      }
    }
  }
}
</script>