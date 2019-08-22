<template>
  <div id="app">
    <!--<wBScroll></wBScroll>-->
    <div style="height:20px; background-color:green;"></div>
    <!--<wIScroll></wIScroll>-->
    <wNiceScroll></wNiceScroll>
    <wCircularGraph></wCircularGraph>
    <!--<wColumn></wColumn>-->
    <wColumnHorizon></wColumnHorizon>
    <wHappyScroll></wHappyScroll>
    <button style="position: fixed;top: 0px; right: 0;" @click="deleteLi">减少数据</button>
  </div>
</template>

<script>
import wBScroll from '@/components/betterScroll/BScroll'
import wIScroll from '@/components/iscroll/Iscroll'
import wNiceScroll from '@/components/niceScroll/NiceScroll'
import wCircularGraph from '@/components/echarts/CircularGraph'
import wColumn from '@/components/echarts/Column'
import wColumnHorizon from '@/components/echarts/ColumnHorizontal'
import wHappyScroll from '@/components/happyScroll/HappyScroll'
export default {
  name: 'App',
  components:{
    wBScroll,
    wIScroll,
    wNiceScroll,
    wCircularGraph,
    wColumn,
    wColumnHorizon,
    wHappyScroll
  },
  methods:{
    deleteLi(){
      //document.querySelector("#nicescroll ul").removeChild(document.querySelectorAll("#nicescroll li")[0])
      document.querySelector("#scrollItemCon ul").removeChild(document.querySelectorAll("#scrollItemCon li")[0])
    }
  }
}
</script>

<style>
html, body, div, span, object, iframe, h1, h2, h3, h4, h5, h6, p, a, img, ol, ul, li, form	 { margin:0; padding:0; border:0; 
list-style:none; font-family:"微软雅黑";}
table, tr,td,dl, dt, dd{ margin:0; padding:0; list-style:none; font-family:"微软雅黑";}
div, span, h1, h2, h3, h4, h5, h6, p, a, img, dl, dt, dd, ol, ul, li, form { overflow:hidden; outline: none;}
input,td,th { margin:0; padding:0; }
h1,h2,h3,h4,h5,h6 {font-size:12px; font-weight:normal;}  
a { text-decoration:none; color:#484849;}
.clear{ clear:both;}
.boxcenter{margin: 0 auto;}
table { border-collapse:collapse;border-spacing: 0; }/*重置表格*/
th{ text-align: left}

</style>
