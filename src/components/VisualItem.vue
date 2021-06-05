<template>
  <div 
  v-bind:items="items">
  <!--for a non-shuffled array -->
  <div v-if="isShuffled==false"> 
  <div :key="item" v-for="item in items">
  <div @click="deleteItem(item)" :key="n" v-for="n in item.amount" class="square" v-bind:style="{ 'background-color':item.color}"> </div> </div>
  </div>
  </div>

  <!-- for a shuffled array-->
  <div v-bind:items="shuffledItems" v-if="isShuffled"> 
  <div :key="item" v-for="item in shuffledItems">
  <div @click="deleteItem(item)" :key="n" v-for="n in item.amount" class="square" v-bind:style="{ 'background-color':item.color}"> </div> </div>
  </div>
</template>

<script>
export default {
  name: 'VisualItem',
  data() {
    return {
    }
  },
  props:['items','isShuffled'],
  methods: {
      deleteItem(item) {
      let idx = this.items.indexOf(item);
      let val = item.amount-1;
      this.$emit('item-deleted', idx, val);
    },
  },
  computed: {
  shuffledItems() {
    console.log(this.items.slice(0).sort(() => Math.random() - 0.5))
    return this.items.slice(0).sort(() => Math.random() - 0.5)
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.square {
    width: 10px;
    height: 10px;
    margin: 1px;
    display: inline-block;
}


</style>
