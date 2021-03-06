// 主页背景与头像
<template>
  <div class="homepage">        
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
      // relativeHeight:'',
      // relativeWidth:'',
      show:false,
      Info:['Coding入门','散装江苏人'],
    }
  },
  created(){
    this.$nextTick(()=>{
      setTimeout(()=>{
            this.show=true
      },100) 
    })
  },
  // watch:{
  //   relativeWidth(relativeWidth){
  //     let that=this
  //     that.relativeWidth=relativeWidth
  //     console.log(that.relativeWidth)
  //   },
  //   relativeHeight(relativeHeight){
  //     let that=this
  //     that.relativeHeight=relativeHeight
  //     console.log(that.relativeHeight)
  //   },

  // },
//   mounted(){
//     var that =this;
//     window.onresize=()=>{
//       return(()=>{
//         window.fullHeight = document.documentElement.clientHeight;
//         window.fullWidth = document.documentElement.clientWidth;        
//         that.relativeHeight=+window.fullHeight+'px';
//         that.relativeWidth=+window.fullWidth+'px';
//         that.homepage.backgroundSize=this.relativeWidth.toString()+' '+this.relativeHeight.toString()
//         //console.log(this.homepage.backgroundSize)              
//       })()
//     }
//   }
// }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
  .Avatar >>>img{
    width:160px
    height:160px
    border-radius:80%;
  }
  .Avatar{
    display: inline-block;
    text-align: center; 
    border-radius: 20px;
    width: 300px;
    height: 350px;
    margin: auto;

    h1{
      font-size: 2em;
      color: #0099ff;
      margin: 3rem auto 1rem;
      .vue-typer{
        display: inline-block;
      }
    }
  }

.fade-enter-active, .fade-leave-active {
  transition: opacity 1.5s ease-in-out;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.homepage{
    top: 0px;  // 这里是设置与顶部的距离
    left: 0px;  // 这里是设置与左边的距离
    width: 100%;
    height: 100%;
    background-image : url('../assets/Home_bg.jpg');
    overflow: hidden;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    display :flex;
    position :relative;
}
</style>


