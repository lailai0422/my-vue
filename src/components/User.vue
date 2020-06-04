<template>
  <div class="hello">
    {{msg}}
    <el-input v-model="input" placeholder="请输入内容"></el-input>
  <treeselect
  :multiple="true"
  :required="true"
  :options="options"
  :disable-branch-nodes="true"
  v-model="value"
  search-nested
  >
   <label  slot="option-label" slot-scope="{ node}" :class="{labelClassName:node.raw.miao}">
   {{ node.label }}
  </label>
  </treeselect>
  <div>
  <treeselect :options="options111" :value="value111" :multiple="multiple">
    <div slot="value-label" slot-scope="{ node }">{{ node.raw.customLabel }}</div>
  </treeselect>
  <p>
    <label><input type="checkbox" v-model="multiple">Multi-select</label>
  </p>
</div>
  </div>  
</template>

<script>
import Treeselect from '@riophae/vue-treeselect'
  // import the styles
import '@riophae/vue-treeselect/dist/vue-treeselect.css'
export default {
   // register the component
  components: { Treeselect },
  data () {
    return {
      labelClassName:true,
      countClassName:true,
    multiple: true,
    value111: null,
    options111: [ 1, 2, 3 ].map(i => ({
      id: i,
      label: `Label ${i}`,
      customLabel: `Custom Label ${i}`,
    })),
      input: '',
      msg: 'I am  child Component',
       value: [],
    options: [ {
      id: 'm',
      label: 'McDonalds',
       miao:true,
      children: [ {
        id: 'm-fries',
        label: 'French Fries',
        miao:true
      }, {
        id: 'm-cheeseburger',
        label: 'Cheeseburger',
        miao:true
      }, {
        id: 'm-white-cheedar-burger',
        label: 'White Cheddar Burger',
         miao:true
      }, {
        id: 'm-southwest-buttermilk-crispy-chicken-salad',
        label: 'Southwest Buttermilk Crispy Chicken Salad',
         miao:true
      }, {
        id: 'm-cola',
        label: 'Coca-Cola®',
         miao:true
      }, {
        id: 'm-chocolate-shake',
        label: 'Chocolate Shake',
         miao:true
      } ],
    }, {
      id: 'kfc',
      label: 'KFC',
       miao:true,
      children: [ {
        id: 'kfc-fries',
        label: 'French Fries',
         miao:true,
      }, {
        id: 'kfc-chicken-litties-sandwiches',
        label: 'Chicken Litties Sandwiches',
         miao:true,
      }, {
        id: 'kfc-grilled-chicken',
        label: 'Grilled Chicken',
         miao:true,
      }, {
        id: 'kfc-cola',
        label: 'Pepsi® Cola',
         miao:false
      } ],
    }, {
      id: 'bk',
      label: 'Burger King',
      miao:false,
      children: [ {
        id: 'bk-chicken-fries',
        label: 'Chicken Fries',
        miao:false
      }, {
        id: 'bk-chicken-nuggets',
        label: 'Chicken Nuggets',
        miao:false
      }, {
        id: 'bk-garden-side-salad',
        label: 'Garden Side Salad',
      }, {
        id: 'bk-cheeseburger',
        label: 'Cheeseburger',
        miao:false
      }, {
        id: 'bk-bacon-king-jr-sandwich',
        label: 'BACON KING™ Jr. Sandwich',
        miao:false
      }, {
        id: 'bk-cola',
        label: 'Coca-Cola®',
        miao:false
      }, {
        id: 'bk-oreo-chocolate-shake',
        label: 'OREO® Chocolate Shake',
        miao:false
      } ],
    } ],
    }
  },
  methods:{
    valueChange(value,instanceId){
    },
    deselect(node){
    }
  },
  // beforeCreate(){
  // alert("beforeCreate----当前组件实例化之前执行的函数");
  // },
  // created(){
  //   alert("created----组件实例化完毕，但是页面还未显示");
  // },
  // boforeMount(){
  //   alert("boforeMount----组件挂在前(模板编译之前)，页面仍然未展示，虚拟的dom已经配置");
  // },
  // mounted(){
  //   alert("mounted----组件挂载后(模板编译完成)，此方法执行后，页面显示");
  // },
  // beforeUpdate(){
  //   alert("beforeUpdate----组件更新前（数据更新之前），页面仍未更新，但是虚拟的dom已经配置");
  // },
  // updated(){
  //   alert("updated----组件更新（数据更新完毕），此方法执行后，页面显示");
  // },
  // beforeDestroy(){
  //   alert("beforeDestroy----组件销毁前（实例销毁之前）");
  // },
  // destroyed(){
  //   alert("destroyed----组件已经销毁（实例销毁完成）");
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hello{
    /* color: red; */
  }
  .countClassName{
    color:red
  }
  .labelClassName{
    color:green
  }
</style>
