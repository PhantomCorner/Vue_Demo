<template>
<!--整体div -->
  <div>
      <!--首页-->
      <div class="layout-header" id='homepage'><Test /></div>
      <!--个人信息-->
      <div class="layout-about" id='about'><AboutMe /></div>

    
  </div>
</template>
<script>

import Test from '@/components/Test.vue'
//import Workexp from '@/components/Workexp.vue'
import AboutMe from '@/components/AboutMe.vue'
export default {
  name: 'Home',
  components: {
    Test,
   AboutMe,
   //Workexp
  },
}
</script>
<style lang="stylus">
body{
  margin :0;
  padding :0;
  font-size:0;
}
.layout-header{
    font-size: 15px;
    
}
.layout-about{
   font-size: 15px;
}

</style>
