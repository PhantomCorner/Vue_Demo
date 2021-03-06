<template>
    <div class="Workexp">
        <Header :Title="Title" :Content="Content"/>
        <ul>
            <li v-for="(item,index) in ExpList" :key="index">
                <div>
                    <span class="ExpTitle">{{item.text}}</span>
                    <br />
                    <span class="ExpSubtitle">{{item.year}}</span>
                    <br />
                    <span class="ExpContent">{{item.content}}</span>
                </div>
            </li>
        </ul>
        <div class="loading"></div>
    </div>

</template>

<script>
import Header from '../components/Header.vue'
export default {
    components:{
        Header,
    },
    data(){
        return{
            Title:'Experience',
            Content:'我的经历',
            ExpList:[
                {text:'新西兰怀卡托大学(University of Waikato) 计算机科学专业', year:'2017.6至2021.6',content:'本科生'}
            ]
        }
    }
}
</script>

<style scoped>
.ExpSubtitle{
    font-size: 12px;
    margin-top: 2px;
}
.loading:after {
  overflow: hidden;
  display: inline-block;
  vertical-align: middle;
  -webkit-animation: ellipsis steps(4,end) 2s infinite;      
  animation: ellipsis steps(4,end) 2s infinite;
  content: "\2026"; /* ascii code for the ellipsis character */
  font-size: 30px;

}

@-webkit-keyframes ellipsis {
    from {
        width: 0px;
    }
    to {
        width: 30px;
    }
}
</style>