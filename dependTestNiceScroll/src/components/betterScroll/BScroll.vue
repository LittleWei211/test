<template>
  <div class="bscroll" ref="bscroll">
    <ul>
        <li>
            <div class="scanTime">
				2019-05-20 02:08:06
            </div>
            <div class="scanResult">
                <p class="finnisnTest">
                    <span>结束检测:</span><span>
                        https://blog.csdn.net/lhq186/article/details/80166436https://blog.csdn.net/lhq186/article
                    </span>
                </p>
                <p class="loopType">
                    <span>漏洞类型:</span>
                    <span>跨站脚本</span>
                    <span>,漏洞个数:</span>
                    <span>18</span>
                    <span>,耗时:</span>
                    <span>17.58</span>s
                </p>
            </div>
            <div class="scanTime">
				2019-05-20 02:08:06
            </div>
            <div class="scanResult">
                <p class="finnisnTest">
                    <span>结束检测:</span><span>
                        https://blog.csdn.net/lhq186/article/details/80166436https://blog.csdn.net/lhq186/article
                    </span>
                </p>
                <p class="loopType">
                    <span>漏洞类型:</span>
                    <span>跨站脚本</span>
                    <span>,漏洞个数:</span>
                    <span>18</span>
                    <span>,耗时:</span>
                    <span>17.58</span>s
                </p>
            </div>
            <div class="scanTime">
				2019-05-20 02:08:06
            </div>
            <div class="scanResult">
                <p class="finnisnTest">
                    <span>结束检测:</span><span>
                        https://blog.csdn.net/lhq186/article/details/80166436https://blog.csdn.net/lhq186/article
                    </span>
                </p>
                <p class="loopType">
                    <span>漏洞类型:</span>
                    <span>跨站脚本</span>
                    <span>,漏洞个数:</span>
                    <span>18</span>
                    <span>,耗时:</span>
                    <span>17.58</span>s
                </p>
            </div>
        </li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
        <li>6</li>
    </ul>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'Bscroll',
  data(){
      return {

      }
  },
  mounted(){
      this.$nextTick(()=>{
          if(!this.scroll){
              this.scroll = new BScroll(this.$refs.bscroll,{
                  click:true
              });
          }else if(!this.$refs.bscroll){
              return 
          }else{
              this.scroll.refresh();
          }
      })
  }
}
</script>

<style>
.bscroll{
    height: 300px;
}
.bscroll li{
    min-height: 100px;
    background-color: red;
    margin-bottom: 20px;
    padding: 10px 0;
}
</style>
