<template>
  <div v-for="list in lists"
    v-bind:list="list" :key="list.id"> 
    Block {{list.id}}
    <VisualItem
    v-bind:id="list.id"
    v-bind:items="items" />
  </div>
</template>

<script>
import VisualItem from './VisualItem.vue'
export default {
  name: 'VisualList',
  props: ['lists','items'],
  components: {
      VisualItem
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
