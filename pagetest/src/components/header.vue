<template>
  <div id="header" v-on:click="titlechange">
    <h2>{{ msg }}-----{{ title }}</h2>
    <p><b>PS:</b>使用了组件传值，点击可以更改标题内容</p>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      msg: '这里是头部header区域'
    }
  },
   props:{
    title:{
      type:String,
      required:true
    }
  },
  methods:{
    titlechange:function(){
      this.msg="titlechange";
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#header{
  color:green;
}
h1, h2, h3 {
  font-weight: normal;padding:10px 0;
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
