<template>
  <div id="contents">
    <h3 class="chead">{{ msg }}</h3>
    <ul>
      <li v-for="(user,index) in users" @key:index >
         <h2>{{user.name}}</h2>
         <h3>{{user.email}}</h3>     
      </li>
    </ul>
    <div class="btn">
          <button class="buttonCon bt1" v-on:click="SendToParent">点击更改父组件app.vue标题title</button> 

          <button class="buttonCon bt2" v-on:click="delate">点击删除当前data数据内容</button>
    </div>

  </div>
</template>

<script>
export default {
  name: 'Contents',
  methods:{
    SendToParent:function(){
     this.$emit("TitleFromChild","title changed by content.vue");
    },
    delate:function(){
       this.users.pop();
    }
  },
  props:{
    users:{
      type:Array,
      required:true
    }
  },
  data () {
    return {
      msg:'这里是contents内容区，下面是内容'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#contents{
  width:100%; 
  margin:0px auto;
  padding:10px 20px;
  box-sizing:border-box;
  color:green;
}
.btn{
   clear:both; 
}

.buttonCon{
  width: 370px; /* 宽度 */
	height: 40px; /* 高度 */
	border-width: 0px; /* 边框宽度 */
	border-radius: 3px; /* 边框半径 */
	background: green; /* 背景颜色 */
	cursor: pointer; /* 鼠标移入按钮范围时出现手势 */
	outline: none; /* 不显示轮廓线 */
	font-family: Microsoft YaHei; /* 设置字体 */
	color: white; /* 字体颜色 */
	font-size: 17px; /* 字体大小 */
  float:left;
}
.bt2{margin-left:20px;}
#contents .chead {
  text-align:left;
}

ul{
  display:flex;
  flex-wrap:wrap;
  list-style-type:none;
  padding:0;
}

li{
  flex-grow:1;
  flex-basis:250px;
  padding:30px;
  border:1px solid green;
  margin:10px;
  height:65px;
}

h1, h2, h3 {
  font-weight: normal;
}


</style>
