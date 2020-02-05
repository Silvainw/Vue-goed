<template>
  <div>
    <div v-bind:key="verlang.id" v-for="verlang in verlangen">
      <VerlangItem v-bind:verlang="verlang" v-on:del-verlang="$emit('del-verlang', verlang.id)" />
    </div>
  </div>
</template>

<script>
import VerlangItem from './VerlangItem.vue';

export default{
    name: "Verlangen",
  components: {
    VerlangItem
  },
  props: ["verlangen"]
}
</script>

<style scoped>

</style>
