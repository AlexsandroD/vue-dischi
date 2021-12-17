<template>
    <div class="card">
        <img :src="info.poster" alt="">
        <h2>{{info.title}}</h2>
        <div class="text">
            <p>{{info.author}}</p>
            <p>{{info.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name:'Card',
    props:{
        info:Object,
    }
}
</script>

<style lang="scss" scoped>
    .card{
        text-align: center;
        // min-height: 360px;
        background-color:#2E3A46 ;
        padding: 15px;
        // margin:20px 10px;

        
        img{
            width: 100%;
        }
        h2{
            color: #fff;
            padding: 10px;
            margin-bottom: 10px;
        }
        .text{

            p{
                color: #7A7B7C;
            }
        }
    }
</style>