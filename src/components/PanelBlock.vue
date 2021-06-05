<template>
  <div
  v-bind:id="id">
      Block {{id}}
      <VisualList 
       @item-deleted="deleteItem"
      v-bind:items="items"/>
      {{items}}
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
         deleteItem(idx, val) {
      this.$emit('item-deleted', idx, val);
    },
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
