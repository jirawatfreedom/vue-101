<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ dataMessage }}</h1>
    <input v-model="dataMessage" />

    <input type="number" v-model.number="a" />
    <input type="number" v-model.number="b" />

    <span>{{ printSum() }}</span>
    <br>
    <span>{{ total }}</span>

    <br>
    <span>DataParent : {{ dataParent }}</span>

    <br>
    <Child @clicked="received" />
  </div>
</template>

<script>
import Child from './Child.vue';
export default {
  components:{
    Child
  },
  data(){
    return {
        dataMessage : 'Hello Test',
        a : 10,
        b: 20,
        dataParent: 'xxx'
    }
  },
  computed:{
    total(){
      return this.a + this.b;
    }
  },
  methods:{
      received(value) {
          this.dataParent = value
      },
    printSum(){
      let x = this.a + this.b
      return x;
    }
  },
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
