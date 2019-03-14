<template>
  <div id="app">

    <h1>{{ msg }}</h1>
    <pageheader v-bind:title = "title"></pageheader>
    <br>
    <contents v-bind:users="users" v-on:TitleFromChild="ChangeTitle"></contents>
    <br>
    <pagefooter v-bind:title = "title"></pagefooter>

  </div>
</template>

<script>

import PageHeader from '@/components/Header'
import Contents from '@/components/Contents'
import PageFooter from '@/components/Footer'


export default {
  name: 'App',
  methods:{
     ChangeTitle:function(title){
        this.msg =title;
     }
  },
  data () {
    return {
      msg: '这里是整个网页的头部标题部分',
      users:[
             
      ],
      title:"父组件中添加新内容"
    }
  },
  components:{
     "contents":Contents,
     "pageheader":PageHeader,
     "pagefooter":PageFooter
  },
  created(){
    this.$http.get("http://jsonplaceholder.typicode.com/users")
    .then((data) => {
      this.users = data.body;
    })
  }
}
</script>

<style >
*{margin:0 auto}
#app {
  width:1200px;
  margin-top:30px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
h1{
  color:green;
}
</style>
