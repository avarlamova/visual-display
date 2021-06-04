<template>
<div id="app">
  <List 
  v-bind:lists="lists"
  v-bind:items="items"
  />
  <VisualPanel
  v-bind:lists="lists"
  v-bind:items="items" />
</div>
</template>

<script>
import List from './components/List.vue'
import VisualPanel from './components/VisualList.vue'
export default {
  name: 'App',
  data(){
    return {
      lists: [
        {id:1, isShown:true},
        {id:2, isShown:false},
        {id:3, isShown:false},
        {id:4, isShown:false},
        ],
      items: [
        {amount: 10, color:'#123456', isChecked: true},
        {amount: 60, color:'#624875', isChecked: true},
        {amount: 42, color:'#664123', isChecked: true},
        {amount: 1, color:'#789235', isChecked: true},
        ],
    }
  },
  methods: {
    toggleList(idx) {
      let list = this.lists[idx-1];
      list.isShown=!list.isShown
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

</style>
