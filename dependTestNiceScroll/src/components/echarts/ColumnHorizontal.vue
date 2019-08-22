<template>
  <div style="height:350px; overflow:hidden">
    <div class="columnHorizon" id="columnHorizon" style="margin-left: 50px;">
    </div>
  </div>
</template>

<script>
  import echarts from 'echarts/lib/echarts'
  import 'echarts/lib/chart/pie'
  import 'echarts/lib/chart/bar'
  import  'echarts/lib/chart/line'
  import 'echarts/lib/chart/radar'
  //import 'echarts/lib/component/tooltip'
  //import 'echarts/lib/component/legend'
  import 'echarts/lib/component/title'

  export default {
    name: 'ColumnHorizon',
    data(){
      return {
        option:{
          legend: {
            show:false
          },
          tooltip: {},
          dataset: {
            //dimensions: ['product', '漏洞数', '已修复', '未修复'],
            source: [
              {product: '靶场2dvwa', 'value': 40},
              {product: '境外API六月版', 'value': 83.1},
              {product: '靶场1', 'value': 86.4},
              {product: 'API模拟器', 'value': 72.4},
              {product: '工银i服务', 'value': 72.4}
            ]
          },
          xAxis: {
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
          grid:{
            x:100
          },
          // Declare several bar series, each will be mapped
          // to a column of dataset.source by default.
          series: [
            {
              type:'bar',
              itemStyle:{
                normal:{
                  barBorderRadius:[100,10,10,10],
                  color:'rgba(0,0,0,0.05)'
                }
              },
              barGap:'-100%',
              barCategoryGap:'50%',
              data:[],
              animation:false,
              barWidth:'20%',

            },
            {
              type: 'bar',
              barWidth:'20%',
              itemStyle:{
                normal: {
                  barBorderRadius:[10,10,10,10],
                  color: function (params) {
                    var colorList = [
                      "#ed1f1f"
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
      this.option.series[0].data = this.option.dataset.source.map(function(item,index){
        return 100
      })
      console.log(this.option.series[0].data);
    },
    mounted(){
      //this.$nextTick(function(){

      const chartObj = echarts.init(document.getElementById('columnHorizon'));
      chartObj.setOption(this.option)
      //});

    }
  }
</script>

<style>
  .columnHorizon{
    width:520px;
    height: 300px;
    overflow: hidden;
  }

</style>
