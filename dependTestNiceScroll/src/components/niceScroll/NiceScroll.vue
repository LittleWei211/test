<template>
<div style="height:350px; overflow:hidden">
  <div class="nicescroll" id="nicescroll">
    <ul>
        <li>nicescroll----11</li>
        <li>nicescroll----22</li>
        <li>nicescroll----33</li>
        <li>nicescroll----44</li>
        <li>nicescroll----55</li>
        <li>nicescroll----66</li>

        <li>nicescroll----11</li>
        <li>nicescroll----22</li>
        <li>nicescroll----33</li>
        <li>nicescroll----44</li>
        <li>nicescroll----55</li>
        <li>nicescroll----66</li>
    </ul>
  </div>
</div>
</template>

<script>
  import $ from 'jquery'
  import 'jquery.nicescroll'
//import NiceScroll from 'jquery.nicescroll'
export default {
  name: 'NiceScroll',
  data(){
      return {

      }
  },
  mounted(){
    console.log(window.NiceScroll);
    var ns = $(".nicescroll").niceScroll({
      cursorcolor:"#efefef",
      autohidemode:false,
      hwacceleration:true
    }).init();
    console.log(ns);
    /*ns.updateScrollBar(function () {
      console.log('滚动条高度更新了！！');
    })*/
  }
}
</script>

<style>
.nicescroll{
    width:420px;
    height: 300px;
    overflow: hidden;
}
.nicescroll li{
    height: 100px;
    background-color: red;
    border-top: 20px solid #fff;
}
</style>
