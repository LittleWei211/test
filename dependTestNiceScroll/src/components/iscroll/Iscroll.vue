<template>
<div style="height:350px; overflow:hidden">
  <div class="bscroll" ref="bscroll">
    <ul>
        <li>11我是iscroll</li>
        <li>22</li>
        <li>33</li>
        <li>44</li>
        <li>55</li>
        <li>66</li>

        <li>11</li>
        <li>22</li>
        <li>33</li>
        <li>44</li>
        <li>55</li>
        <li>66</li>

        <li>11</li>
        <li>22</li>
        <li>33</li>
        <li>44</li>
        <li>55</li>
        <li>66</li>
    </ul>
  </div>
</div>
</template>

<script>
import IScroll from 'iscroll'
export default {
  name: 'Iscroll',
  data(){
      return {

      }
  },
  mounted(){
      this.$nextTick(()=>{
          let iscroll = new IScroll('.bscroll',{
              scrollbars:true,
              bounce:true,
              mouseWheel:true,
              probeType:3,
              vScroll:true
          });
      })
  }
}
</script>

<style>
.bscroll{
    width:420px;
    height: 300px;
    overflow: hidden;
}
.bscroll li{
    height: 100px;
    background-color: red;
    margin-bottom: 20px;
}
</style>
