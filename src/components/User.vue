<template>
  <div class="hello">
    {{msg}}
    <el-input v-model="input" placeholder="请输入内容"></el-input>
  </div>  
</template>

<script>
export default {
  data () {
    return {
      input: '',
      msg: 'I am  child Component'
    }
  },
  methods:{
    valueChange(value,instanceId){
    },
    deselect(node){
    }
  },
  beforeCreate(){
  alert("beforeCreate----当前组件实例化之前执行的函数");
  },
  created(){
    alert("created----组件实例化完毕，但是页面还未显示");
  },
  boforeMount(){
    alert("boforeMount----组件挂在前(模板编译之前)，页面仍然未展示，虚拟的dom已经配置");
  },
  mounted(){
    alert("mounted----组件挂载后(模板编译完成)，此方法执行后，页面显示");
  },
  beforeUpdate(){
    alert("beforeUpdate----组件更新前（数据更新之前），页面仍未更新，但是虚拟的dom已经配置");
  },
  updated(){
    alert("updated----组件更新（数据更新完毕），此方法执行后，页面显示");
  },
  beforeDestroy(){
    alert("beforeDestroy----组件销毁前（实例销毁之前）");
  },
  destroyed(){
    alert("destroyed----组件已经销毁（实例销毁完成）");
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hello{
    color: red;
  }
</style>
