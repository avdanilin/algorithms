<template>
  <section class="selection-sort">
    <h2 class="title">{{ title }}</h2>

    <input
        class="input input_large"
        type="text"
        :placeholder="`Write some unsorted series of numbers through, - 1,4...`"
        v-model="inputValue"
    >
    <button @keydown.enter="selectionSort" @click="selectionSort">
      Сортировать массив
    </button>
    <div v-if="array.length">
      array is sorted - {{ array }}!
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Selection sort'
    },
  },
  data() {
    return {
      inputValue: null,
      array: [],
    }
  },
  methods: {
    generateArray() {
      try {
        let array = this.array
        array.length = 0
        let getArray = this.inputValue.split(',')
        getArray.map(element => array.push(parseInt(element)))
      } catch (e) {
        alert('write at least one number from a series of numbers!')
      }
    },
    selectionSort() {
      this.generateArray()
      let array = this.array

      for (let j = 0; j < array.length - 1; j++) {

        let max = -Infinity
        let index = null

        for (let i = 0; i < array.length - j; i++) {
          if (array[i] > max) {
            max = array[i]
            index = i
          }
        }

        const buffer = array[array.length - 1 - j]
        array[array.length - 1 - j] = max
        array[index] = buffer
      }

      return array
    }
  }
}
</script>

<style scoped>

</style>