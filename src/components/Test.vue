// 主页背景与头像
<template>
  <div class="homepage" >
    <div class="Avatar">
        <transition name='fade'>
          <img src= '@/assets/Avatar.jpg' v-if='show' />     
        </transition>
          <h1>     
            <vue-typer :text='Info' :type-delay='250'></vue-typer>
          </h1>
    </div>

  </div>
  
</template>

<script>
import {VueTyper} from 'vue-typer'

export default {
  name: 'Test',
  components:{
    VueTyper
  },
  data(){
    
    return{
      show:false,
      Info:['散装江苏人','普普通通留学生'],
    }
  },
  created(){
    this.$nextTick(()=>{
      setTimeout(()=>{
            this.show=true
      },100) 
    })
  },
}
</script>

<style scoped lang="stylus">
  .Avatar{
    margin :0 auto;
    width: auto;
    height:300px;
    text-align :center;

    h1{
      font-size: 2em;
      color: #0099ff;
      margin: 3rem auto 1rem;
      .vue-typer{
      }
    }
    img{
      width:160px
      height:160px
      border-radius:80%;
    }
  }

.fade-enter-active, .fade-leave-active {
  transition: opacity 1.5s ease-in-out;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.test{
  background-color :green;
  text-align :center;
}
.homepage{
        height:100vh;
        display :flex;
        position:relative;
        background-image : url('../assets/Home_bg.jpg');
        background-repeat: no-repeat;
        background-size :cover;
        align-items: center;
}
</style>


