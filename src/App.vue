<template>
<div id="app">
  <div class="left">
  <List 
  v-bind:lists="lists"
  v-bind:keys="keys"
  v-bind:items="items"
  @amount-changed="changeItemAmount"
  />
  </div>
  <div class="right">
  <VisualPanel
  @item-deleted="deleteItem"
  v-bind:lists="lists"
  v-bind:items="items" />
  </div>
</div>
</template>

<script>
import List from './components/List.vue'
import VisualPanel from './components/VisualList.vue'
export default {
  name: 'App',
  data(){
    return {
      keys: [1,2,3,4,5,6,7,8,9,10],
      lists: [
        {id: 1, isShown:true},
        {id: 2, isShown:false},
        {id:3, isShown:false},
        {id:4, isShown:false},
        {id:5, isShown:false},
        ],
      lengthRange: [4,5,6,7,8,9,10],
      items: [
        {amount: Math.floor( Math.random() * 100), color:'#800000', isChecked: true},
        {amount: Math.floor( Math.random() * 100), color:'#0000FF', isChecked: true},
        {amount: Math.floor( Math.random() * 100), color:'#00FF00', isChecked: true},
        {amount: Math.floor( Math.random() * 100), color:'#FFFF00', isChecked: true},
        ],
    }
  },
  methods: {
      changeItemAmount(idx,val) {
        console.log(idx, val)
        this.items[idx]['amount'] = parseInt(val);
      },
      deleteItem(idx,val) {
        this.items[idx]['amount'] = parseInt(val);
      }
  },
  components: {
    List,
    VisualPanel
  }
}
</script>

<style>
#app {
  margin-top: 60px;
}

.left {
  width: 60%;
  float: left;
}

.right {
  width: 40%;
  float: right;
}
</style>
