<template>
<div 
  v-bind:items="items">
  <!--for a non-shuffled array -->
  <div v-if="isShuffled==false"> 
    <div :key="item" v-for="item in items">
      <div class="form-row" v-for="x in item.amount" :key="x">
        <div 
        v-if="item.isChecked" 
        @click="deleteItem(item)" 
        class="square" 
        v-bind:style="{ 'background-color':item.color}"> 
        </div> 
      </div>
    </div>
  </div>
</div>

  <!-- for a shuffled array-->
  <div v-if="isShuffled"> 
    <div :key="item" v-for="item in shuffledItems">
      <div class="form-row" v-for="x in item.amount" :key="x">
        <div 
        v-if="item.isChecked" 
        @click="deleteItem(item)" 
        class="square" 
        v-bind:style="{ 'background-color':item.color}"> 
        </div> 
      </div>
    </div>
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
     return this.items.slice(0).sort(() => Math.random() - 0.5)
  },
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
.form-row {
  display: inline-block;
}


</style>
