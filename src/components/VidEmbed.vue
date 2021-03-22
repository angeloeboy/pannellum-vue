<template>
    <div class="outer" @click="showVid">
         <div class="inner">
            <img :src="img" alt="">
             <h1>This is an embedded vid from Youtube</h1>
            <iframe width="560" height="315" src="https://www.youtube.com/embed/MpJIg_3DnLk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
    </div>
</template>

<script>

import img from "../assets/close.png"

export default {

    
    data(){
        return{
            img: img
        }
    },

    props: {
        testingClicked: {
            type: Function
        }
    },

    methods: {
        showVid(){
            this.$emit('onShowVidClicked')
        }
    }
}
</script>
<style scoped>


    .outer{
        position: absolute;
        top: 0;
        width: 100vw;
        height: 100vh;
        background-color: #00000056;
        z-index: 99;
      
    }
    .inner{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 50%;
        height: 50%;
        background-color: white;
          transition: all 0.3s;
        padding: 50px;
        border-radius: 10px;
    }

    h1{
        text-align: center;
        margin: 0px;
    }


    iframe{
        display: block;
        margin: 0 auto;
        width: 90%;
        margin-top: 20px;
    }

    img{
        width: 20px;
        height: 20px;

        position: absolute;
        top: 20px;
        right: 20px;
    }

</style>