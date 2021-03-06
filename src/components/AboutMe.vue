<template>
<div class="About">
    <div class="About-left">
        <div class="menu">
            <ul>
                <li v-for="(item,index) in MenuItem" :key="index" @click="JumpTo(item.location)">
                    <img :src=(item.img) />{{item.text}}
                </li>
                <li>
                    <img style="width:40px height:40px" src="../assets/JianShu.jpg"/><a href="https://www.jianshu.com/u/a647b65d7401" target="_blank" style="text-decoration:none;color:black">我的简书</a>
                </li>
            </ul>
        </div>
    </div>
    <div class="About-right">
        <Header :Title="Title" :Content="Content"/>
        <div class="Content">
            <div>            
                <img :src="img" >
            </div>
            <div class="ContentMe">
                <p>2017年，就读于新西兰怀卡托大学计算机科学专业。</p>
                <p>平平无奇四年留学，也结识了不少好朋友。</p>
                <p>在校期间接触前端。了解Mysql,Jquery,API调用基础,
                    熟悉H5,Css,Js代码规范</p>
                <p>注重代码整洁,对新技术富有热情</p>
                <p>希望能在工作中提升自己的技术水平，精益求精。</p>
            </div>
        </div>
    </div>
    <div class="Workexp">
        <Workexp />
    </div>
</div>
    
</template>
<script>
import Header from '@/components/Header.vue'
import Workexp from '@/components/Workexp.vue'
export default {
    name:'AboutMe',
    components:{
        Header,
        Workexp

    },
    created(){
        this.imgLoop()
    },
    data(){
        return{
            MenuItem:[
                {text:'首页',img:require('../assets/home.png'),location:'homepage'},
                {text:'关于我',img:require('../assets/user.png'),location:'about'},
            ],

            Title:'普普通通留学生',
            Content:'About Me',

            imgList:[
                {
                    src:require('../assets/img1.jpg')
                },
                {
                    src:require('../assets/img2.jpg')
                },
                // {
                //     src:require('../assets/img3.jpg')
                // }
            ],
            img:'',
            id:0
        }
    },
    methods:{
        JumpTo:function(location){
            var whereTo=document.getElementById(location);
            whereTo.scrollIntoView({behavior: "smooth"});
        },
        imgLoop(){
            this.img=this.imgList[this.id].src
            setInterval(()=>{
                if(this.id===this.imgList.length-1){
                    this.id=0
                    this.img=this.imgList[0].src
                }
                else{
                    this.id+=1;
                    this.img=this.imgList[this.id].src
                }
           },5000)
        }
    },
    
}
</script>
<style scoped>
.About{
    width: 100%;
    height: 100%;
    display:flex;
    margin: 0;

}
.About-left{
    background-color :white;
    width: auto;
    height:100vh;
    line-height: 80px;
    cursor:pointer;
    -webkit-font-smoothing: antialiased;
    font-family: -apple-system,BlinkMacSystemFont,Helvetica Neue,Helvetica,PingFang SC,Hiragino Sans GB,Microsoft YaHei,微软雅黑,Arial,sans-serif;
    
}
.About-right{
    flex: 1;
    height: 100%;
    display: inline-block;

}
.menu{
     font-size: 1.3em;
     font-weight: 500;
     width: 170px;
     height: 100vh;
     text-align: center;
     position:relative;
    float: left;


}
.menu img{
    height: 20px;
    padding: right;
    margin-right: 10px;
}
.menu ul{
    list-style:none;
    display: inline-block;
    margin:0;
    padding:0;

}

.menu li{
 border-bottom:gray 1px dashed;
}
.Content img{
    width: 85%;
    float: left;
    display: block;
    border-radius: 5px;
    flood-opacity: 2px;
}
.ContentMe{
    float: left;
    font-size: 20px;
    line-height: 30px;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

</style>

