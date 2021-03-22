<template>
    <div class="outer" @click="close">
        <div class="inner">
            <h1>This is a simple quiz</h1>

            <p>1. Lorem ipsum dolor sit amet, consectetur adipiscing elit?</p>
            <input type="text">
            <p>2. In ac sodales felis. Etiam lectus lectus, lobortis ac lorem at?</p>
            <input type="text">
            <p>3. Mollis tincidunt nisi?</p>
            <input type="text">
            <p>4. Aliquam iaculis nisi egestas ligula porta tincidunt?</p>
            <input type="text">
            <p>5. Aenean rutrum sit amet nulla vel tincidunt?</p>
            <input type="text">
            <img :src="img" alt="">

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

    methods:{
        close(){
            this.$emit('onShowQuizClicked')
            
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
        width: 30%;
        height: 50%;
        background-color: white;
          transition: all 0.3s;
        padding: 50px;
        border-radius: 10px;

        overflow-y: scroll;
    }

    h1{
        text-align: center;
        margin: 0px;
        color: black;
    }

    p{
        margin-top: 20px;
    }
    input{
        width: 100%;
    }

    img{
        width: 20px;
        height: 20px;

        position: absolute;
        top: 20px;
        right: 20px;
    }
</style>