<template>
  <div class="hello">
    <h3 v-if="msg">{{ msg }}</h3>
    <div v-else>Msg is not defined</div>
    <div>{{ first }}</div>
    <input type="text" v-model="first">
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
      first: 2
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
