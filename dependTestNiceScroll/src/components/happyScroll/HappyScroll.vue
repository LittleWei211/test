<template>
  <div class="happyScroll" style="height:100px; width: 300px; background-color: #ccc;">
    <happy-scroll color="rgba(0,0,0,0.5)" scroll-left.sync="100" size="5" resize>
      <div id="scrollItemCon">
        <ul>
          <li>happyScroll----11</li>
          <li>happyScroll----22</li>
          <li>happyScroll----33</li>
          <li>happyScroll----44</li>
          <li>happyScroll----55</li>
          <li>happyScroll----66</li>

          <li>happyScroll----11</li>
          <li>happyScroll----22</li>
          <li>happyScroll----33</li>
          <li>happyScroll----44</li>
          <li>happyScroll----55</li>
          <li>happyScroll----66</li>
        </ul>
      </div>

    </happy-scroll>
  </div>

</template>

<script>
  /*import Vue from 'vue'
  import { HappyScroll } from 'vue-happy-scroll'
  Vue.use(HappyScroll)*/
  export default {
    name: "HappyScrolls",
    data(){
      return {}
    },
    components:{
      //HappyScroll
    },
    methods:{},
    mounted(){}

  }
</script>

<style scoped>

</style>
