<template>
  <div v-for="list in lists"
  :key="list.id"> 
  Block {{list.id}}
  <button v-if="isShuffled===false" @click="shuffle()"> Shuffle </button>
  <button v-if="isShuffled" @click="shuffle()"> Sort </button>

    <VisualItem
    v-if="list.isShown"
    v-bind:items="items"
    v-bind:isShuffled="isShuffled"
    @item-deleted="deleteItem" />
    
  </div>
</template>

<script>
import VisualItem from './VisualItem.vue'
export default {
  name: 'VisualList',
  data() {
    return {
      isShuffled:false,
    }
  },
  props: ['lists', 'items'],
  components: {
      VisualItem
  },
  methods: {
    shuffle() {
      this.isShuffled = !this.isShuffled
    },
    deleteItem(idx, val) {
      this.$emit('item-deleted', idx, val);
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
