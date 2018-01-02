<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="callParentFn">emit</button>
    <p>这是{{message}}</p>
  </div>
</template>

<script>
export default {
	props:["message"],//接受父页面传来的参数
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods:{
  	callParentFn(){
  		this.$emit("Emit","im emit")
  	}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
.hello{border: 1px solid #ddd;}
</style>
