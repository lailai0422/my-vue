<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <!-- <template>
      <el-radio v-model="radio" label="1">备选项</el-radio>
      <el-radio v-model="radio" label="2">备选项</el-radio>
    </template> -->
    <!-- <User/> -->
    <div id="myChart" style="width: 600px;height:400px;"></div>
  </div>
</template>

<script>
import User from './User'
export default {
  components:{
    User
  },
  name: 'HelloWorld',
  data () {
    return {
      // msg: 'Welcome to Vue.js App of laichunyan  ',
      // radio: '1',
      pictureData: {
    title: {
        text: 'Graph 简单示例'
    },
    tooltip: {},
    animationDurationUpdate: 1500,
    animationEasingUpdate: 'quinticInOut',
    series: [
        {
            type: 'graph',
            layout: 'none',
            symbolSize: 50,
            roam: true,
            focusNodeAdjacency: true,
            label: {
                show: true
            },
            edgeSymbol: ['circle', 'arrow'],
            edgeSymbolSize: [4, 10],
            edgeLabel: {
                fontSize: 20
            },
            data: [{
                name: '节点1',
                x: 300,
                y: 300,
                   itemStyle: {                         // 各圆圈自定义样式
                        normal: {
                                  borderColor: '#b457ff',
                                  color:"blue",
                                  borderWidth: 1,
                                  shadowBlur: 20,
                                  shadowColor: '#b457ff',
                               }
                            }
            }, 
            {
                name: '节点2',
                x: 800,
                y: 300
            }, {
                name: '节点3',
                x: 550,
                y: 100
            }, {
                name: '节点4',
                x: 550,
                y: 500
            }],
            // links: [],
            links: [
            //   {
            //     source: 0,
            //     target: 1,
            //     symbolSize: [5, 20],
            //     label: {
            //         show: true
            //     },
            //     lineStyle: {
            //         width: 5,
            //         curveness: 0.2
            //     }
            // },
              {
                source: '节点1',
                target: '节点2',
                symbolSize: [5, 20],
                label: {
                    show: true,
                    color:"red"
                },
                lineStyle: {
                    width: 5,
                    curveness: 0.2
                }
            },
            
             {
                source: '节点2',
                target: '节点1',
                label: {
                    show: true
                },
                lineStyle: {
                  width: 5,
                    curveness: 0.2
                }
            }, {
                source: '节点1',
                target: '节点3'
            }, {
                source: '节点2',
                target: '节点3'
            }, {
                source: '节点2',
                target: '节点4'
            }, {
                source: '节点1',
                target: '节点4'
            }],
            lineStyle: {
                opacity: 0.9,
                width: 2,
                curveness: 0
            }
        }
    ]
}
    }
  },
mounted(){
  this.drawLine();
},
methods:{
  drawLine(){
        // 基于准备好的dom，初始化echarts实例
        let myChart = this.$echarts.init(document.getElementById('myChart'));
        // 绘制图表
        myChart.setOption(this.pictureData);
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
</style>
