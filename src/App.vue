<template>
  <section class="index">
    <div class="index__items">
      <BinarySearch v-bind="binarySearch"/>
    </div>
  </section>
</template>

<script>
import BinarySearch from "@/components/BinarySearch";

export default {
  name: 'App',
  components: {
    BinarySearch
  },
  data () {
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
}
</style>