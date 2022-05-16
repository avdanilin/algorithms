<template>
  <section class="index">
    <div class="index__items">
      <BinarySearch v-bind="binarySearch"/>

      <SelectionSort/>

      <recursion/>
    </div>
  </section>
</template>

<script>
import BinarySearch from "@/components/BinarySearch";
import SelectionSort from "@/components/SelectionSort";
import recursion from "@/components/recursionComponent.vue";

export default {
  name: 'App',
  components: {
    SelectionSort,
    BinarySearch,
    recursion
  },
  data() {
    return {
      binarySearch: {
        from: 0,
        to: 50
      }
    }
  }
}
</script>
<style lang="scss">
.input {
  width: 16rem;

  &_large {
    width: 22rem;
  }
}
</style>