<template>
<div>
  <ul
  v-for="list in lists"
  v-bind:list="list" :key="list.id"> 
    <li>
    <input type="checkbox" 
    v-model="list.isShown"
    >  
    List {{list.id}}
      <ul v-if="list.isShown">
      <Item v-bind:items="items" />
      </ul>
    </li>
  </ul>
</div>
</template>

<script>
import Item from './Item'
export default {
  name: 'List',
  props:['lists', 'items'],
  components: {
      Item
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
   list-style-type: none
}
.circle-check {
  list-style-type: circle
}
</style>
