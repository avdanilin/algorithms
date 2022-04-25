<template>
  <section class="index">
    <div class="index__items">
      <BinarySearch v-bind="binarySearch"/>

      <SelectionSort/>
    </div>
  </section>
</template>

<script>
import BinarySearch from "@/components/BinarySearch";
import SelectionSort from "@/components/SelectionSort";

export default {
  name: 'App',
  components: {
    SelectionSort,
    BinarySearch
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