<template>
<div style="height:400px; overflow:hidden">
  <div class="circleGraph" id="circleGraph">
    
  </div>
</div>
</template>

<script>
import echarts from 'echarts/lib/echarts'
//import 'echarts/lib/chart/line'
//import 'echarts/lib/chart/pie'
//import 'echarts/lib/chart/bar'
//import 'echarts/lib/chart/radar'
//import 'echarts/lib/component/tooltip'
//import 'echarts/lib/component/legend'
//import 'echarts/lib/component/title'


export default {
  name: 'CircleGraph',
  data(){
        return {
            option:{
                tooltip: {
                    trigger: 'item',
                    formatter: "{a} <br/>{b}: {c} ({d}%)"
                },
                /*legend: {
                    orient: 'vertical',
                    x: 'left',
                    data:['直接访问','邮件营销','联盟广告','视频广告','搜索引擎']
                },*/
                color:['red','blue','gray','yellow','pink'],
                series: [
                    {
                        name:'访问来源',
                        type:'pie',
                        radius: ['50%', '70%'],
                        avoidLabelOverlap: false,
                        label: {
                            normal: {
                                show: true,
                                position: 'outer'
                            },
                            emphasis: {
                                show: true,
                                textStyle: {
                                    fontSize: '16',
                                    fontWeight: 'bold'
                                }
                            }
                        },
                        labelLine: {
                            show:true,
                            normal: {
                                show: true,
                                lineStyle: {
                                  //color: 'red',
                                },
                            }
                        },
                        data:[
                            {value:335, name:'直接访问'},
                            {value:310, name:'邮件营销'},
                            {value:234, name:'联盟广告'},
                            {value:135, name:'视频广告'},
                            {value:1548, name:'搜索引擎'},

                        ]
                    }
                ]
            }
        }
  },
  mounted(){
    //this.$nextTick(function(){
        
        const chartObj = echarts.init(document.getElementById('circleGraph'));
        chartObj.setOption(this.option)
    //});
    
  }
}
</script>

<style>
.circleGraph{
    width:420px;
    height: 300px;
    overflow: hidden;
    width: 100%;
    height: 100%;
}

</style>
