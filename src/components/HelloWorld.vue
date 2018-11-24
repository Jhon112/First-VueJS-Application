<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div class="list-container">
      <h1>Compras del Black Friday</h1>
      <p v-for="item in shoppings" :key="item.id">
        {{ item.title }}
      </p>
    </div>
  </div>

</template>

<script>
import axios from 'axios';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
    shoppings: []
    }
  },
  beforeCreate() {
    
  },
  async created() {
    console.log('beforeCreate', 1);
    const url = 'http://jsonplaceholder.typicode.com/posts';
    const { data } = await axios.get(url)
      // .catch(() => ({ status: false }))
    this.shoppings = data

  console.log('beforeCreate', 2, this.shoppings);
  console.log('beforeCreate', 3); 
  },
  beforeMount() {
    console.log('beforeCreate', this.msg);
  },
  mounted() {

  },
  beforeUpdate() {

  },
  updated() {

  },
  beforeDestroy() {

  },
  destroyed() {

  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.list-container {
  background-color: black;
  color: white;
}
</style>
