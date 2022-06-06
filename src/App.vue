<template>
  <section class="index">
    <div class="index__items">
      <BinarySearch v-bind="binarySearch"/>

      <SelectionSort/>

      <recursion-component/>

      <MaximumNumber />
    </div>
  </section>
</template>

<script>
import BinarySearch from "@/components/BinarySearch";
import SelectionSort from "@/components/SelectionSort";
import RecursionComponent from "@/components/recursionComponent";
import MaximumNumber from "@/components/maximumNumber";

export default {
  name: 'App',
  components: {
    MaximumNumber,
    RecursionComponent,
    SelectionSort,
    BinarySearch,
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