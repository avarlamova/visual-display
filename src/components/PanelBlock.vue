<template>
  <div
  v-bind:id="id">
      Block {{id}}
      <VisualList 
      v-bind:items="items"/>
  </div>
</template>

<script>
import VisualList from './VisualList'
export default {
  name: 'PanelBlock',
  props:['lists', 'items', 'id'],
  components: {
    VisualList
  },
  methods: {
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.square {
    width: 10px;
    height: 10px;
    background-color: red;
    margin: 1px;
}
</style>
