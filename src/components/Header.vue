<template>
    <div class="header">
        <div class="headerTitle">
            <span>{{Title}}</span>
        </div>
        <div class="headerContent">
            <p>{{Content}}</p>
        </div>

    </div>
</template>

<script>
export default {
    name:'Header',
    
    props:{
        Title:String,
        Content:String,
    }
}
</script>

<style scoped>
    .header {
        border-left: 6px solid #E3872D;
        padding: .5em 0 0 1.5em;
        font-family: 'Montserrat', sans-serif;
        margin-bottom: 30px;
        display:inline-block;
    }
    .header span{
        font-size: 18px;
        text-transform: uppercase;
        font-weight: 400;
        letter-spacing: 5px;      
    }
    .header p{
        font-size: 25px;
        text-transform: uppercase;
        font-weight: 400;
        letter-spacing: 5px;      
    }
</style>