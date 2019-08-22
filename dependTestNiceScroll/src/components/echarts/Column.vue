<template>
  <div style="height:350px; overflow:hidden">
    <div class="column" id="column">
    </div>
  </div>
</template>

<script>
  import echarts from 'echarts/lib/echarts'
  import 'echarts/lib/chart/pie'
  import 'echarts/lib/chart/bar'
  import  'echarts/lib/chart/line'
  import 'echarts/lib/chart/radar'
  import 'echarts/lib/component/tooltip'
  import 'echarts/lib/component/legend'
  import 'echarts/lib/component/title'

  export default {
    name: 'Column',
    data(){
      return {
        option:{
          legend: {
            show:true
          },
          tooltip: {
            show:true
          },
          dataset: {
            dimensions: ['product', '漏洞数', '已修复', '未修复'],
            //dimensions: [],
            source:[]
          },
          xAxis: {
            type: 'category',
            axisLine:{
              show:false
            },
            splitLine:{
              show:false
            },
            axisTick:{
              show:false
            },
          },
          yAxis: {
            axisLine:{
              show:false
            },
            splitLine:{
              show:true,
              lineStyle:{
                color:'#eee'
              }
            },
            axisTick:{
              show:false
            },
          },
          // Declare several bar series, each will be mapped
          // to a column of dataset.source by default.
          series: [
            {
              type: 'bar',
              barWidth:'10%',
              itemStyle:{
                normal: {
                  barBorderRadius:[10,10,0,0],
                  color: function (params) {
                    var colorList = [
                      "#ed1f1f"
                    ];
                    return colorList[params.dataIndex]
                  }
                }
              }
            },
            {
              type: 'bar',
              barWidth:'10%',
              itemStyle:{
                normal: {
                  barBorderRadius:[10,10,0,0],
                  color: function (params) {
                    var colorList = [
                      "#d6cece"
                    ];
                    return colorList[params.dataIndex]
                  }
                }
              }
            },
            {
              type: 'bar',
              barWidth:'10%',
              itemStyle:{
                normal: {
                  barBorderRadius:[10,10,0,0],
                  color: function (params) {
                    var colorList = [
                      "#d8c00f"
                    ];
                    return colorList[params.dataIndex]
                  }
                }
              }
            }
          ]
        }
      }
    },
    created(){
      var dataArr = [
        {product: 'high', 'vulNum': 40, 'fixed': 0, 'unfixed': 40},
        {product: 'middle', 'vulNum': 83.1, 'fixed': 0, 'unfixed': 55.1},
        {product: 'low', 'vulNum': 86.4, 'fixed': 0, 'unfixed': 82.5},
        {product: 'tips', 'vulNum': 72.4, 'fixed': 0, 'unfixed': 39.1}
      ];
      //Object.keys(dataArr[0]).map(()=>{})
      //this.option.dataset.dimensions = Object.keys(dataArr[0]);
      this.option.dataset.source = dataArr.map(function(item,index){
        return {
          product:this[index],
          '漏洞数':item.vulNum,
          '已修复':item.fixed,
          '未修复':item.unfixed
        }
      },['高危','中危','低危','提示']);
    },
    mounted(){
      //this.$nextTick(function(){

      const chartObj = echarts.init(document.getElementById('column'));
      chartObj.setOption(this.option)
      //});

    }
  }
</script>

<style>
  .column{
    width:420px;
    height: 300px;
    overflow: hidden;
  }

</style>
