<template>
<div key="list.id">
  <ul
  v-for="list in lists" :key="list.id"
  v-bind:items="items"> 
    <li>
    <input type="checkbox" 
    v-model="list.isShown"
    >  
    List {{list.id}} 

      <ul v-if="list.isShown">
      <Item 
      @amount-changed="changeItemAmount"
      v-bind:items="items"/>
      </ul>
      
    </li>
  </ul>
</div>
</template>

<script>
import Item from './Item'
export default {
  name: 'List',
  data() {
    return {
    }
  },
  props:['lists','items','lengths'],
  components: {
      Item
  },
  methods: {
    changeItemAmount(idx,val) {
      this.$emit('amount-changed', idx, val);
  },
    checkAll(){
    }
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
   list-style-type: none
}

</style>
