<template>
  <div id="footer" v-on:click="titlechange">
    <h1>{{ msg }}-----{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  data () {
    return {
      msg: '这里是footer底部区域'
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

#footer{border:1px solid white }
h1, h2, h3 {
  font-weight: normal;padding:10px 0;color:green;
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
