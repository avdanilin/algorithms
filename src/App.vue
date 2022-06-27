<template>
  <section class="index">
    <div class="index__items">
      <BinarySearch v-bind="binarySearch"/>

      <SelectionSort/>

      <recursion-component/>

      <MaximumNumber />

      <QuickSort />
    </div>
  </section>
</template>

<script>
import BinarySearch from "@/components/BinarySearch";
import SelectionSort from "@/components/SelectionSort";
import RecursionComponent from "@/components/RecursionComponent";
import MaximumNumber from "@/components/MaximumNumber";
import QuickSort from "@/components/QuickSort";

export default {
  name: 'App',
  components: {
    MaximumNumber,
    RecursionComponent,
    SelectionSort,
    BinarySearch,
    QuickSort,
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