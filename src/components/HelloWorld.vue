<template>
  <div class="hello">
    <h3 v-if="msg">{{ msg }}</h3>
    <div v-else>Msg is not defined</div>
    <div>{{ first }}</div>
    <input type="text" v-model="first">
    <ul>
      <li v-for="(item, i) in arr" :key="item" @click="deleteFromArr(i)">
        {{item}} - {{i}}
      </li>
    </ul>
    <button @click="someFunc('Hello')">Hello button</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      first: 2,
      arr: [1,2,3,4,5],
      obj: {
        a: 1,
        b: 2,
        c: 3
      }
    }
  },
  methods: {
    someFunc(a) {
      console.log(a)
      this.arr.push(this.arr[this.arr.length -1] + 1)
      this.arr.unshift(this.arr[this.arr.length -1] + 1)
    },
    deleteFromArr(index) {
      this.arr.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
  height: 10px;
  width: 10px;
  background: red;
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
