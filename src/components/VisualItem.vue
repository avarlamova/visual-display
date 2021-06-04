<template>
  <div v-bind:items="items">
      <div class="square"> </div>
  </div>
</template>

<script>
export default {
  name: 'VisualItem',
  props:['items', 'id', 'color', 'amount'],
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
