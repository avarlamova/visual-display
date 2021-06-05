<template>
  <li v-for="item in items"
  v-bind:items="items" 
  :key="item.key"> 
  <input type="checkbox" v-model="item.isChecked">
  <input @change="onAmountChange(item)" type="number" v-model="item.amount"> 
  <input type="color" v-model="item.color">
  </li>
</template>

<script>
export default {
  name: 'Item',
  props: ['items'],
  data() {
    return {
      color: '',
      amount: '',
    }
  },
  methods: {
    onAmountChange(item) {
      let idx = this.items.indexOf(item);
      let init = item.amount;
      let val = parseInt(init)
      this.$emit('amount-changed', idx, val);
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
input[type='number'] {
  border:none;
     margin-left: 50px;
}
input[type='color'] {
  border:none;
  width: 30px;
  height: 30px;
}
li {
   list-style-type: none;
}

</style>
