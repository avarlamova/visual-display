<template>
  <li v-for="item in items"
v-bind:item="item" :key="item.color"> 
<input type="checkbox" v-model="item.isChecked">
  <input @change="onAmountChange" type="number" v-model="item.amount"> 
  <input @change="onColorChange" type="color" v-model="item.color">
  </li>
</template>

<script>
export default {
  name: 'Item',
  props: ['items'],
  methods: {
    onColorChange() {
      'color changed'
    },
    onAmountChange() {
      'amount changed'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
li {
   list-style-type: none
}

a {
  color: #42b983;
}
</style>
