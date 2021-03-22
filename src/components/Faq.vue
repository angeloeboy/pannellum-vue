<template>
    <div class="outer" @click="showFaq">
         <div class="inner">
            <h1>Frequently Asked Questions</h1>
            <h4>1. Lorem ipsum dolor sit amet? </h4>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec tincidunt
              mauris metus, ut posuere ligula pulvinar eget. In fermentum mollis
              mauris et condimentum. Mauris nec mauris eu risus varius convallis.
              Aliquam ut varius turpis, sed condimentum sem.
            </p>
            <h4>2. Lorem ipsum dolor sit amet? </h4>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec tincidunt
              mauris metus, ut posuere ligula pulvinar eget. In fermentum mollis
              mauris et condimentum.
            </p>
            <h4>3. Lorem ipsum dolor sit amet? </h4>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec tincidunt
              mauris metus, ut posuere ligula pulvinar eget. In fermentum mollis
              mauris et condimentum. Mauris nec mauris eu risus varius convallis.
              Aliquam ut varius turpis, sed condimentum sem. Mauris nec mauris eu
              risus varius convallis. Aliquam ut varius turpis, sed condimentum sem.
            </p>
            <h4>4. Lorem ipsum dolor sit amet? </h4>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec tincidunt
              mauris metus, ut posuere ligula pulvinar eget. In fermentum mollis
              mauris et condimentum. Mauris nec mauris eu risus varius convallis.
              Aliquam ut varius turpis, sed condimentum sem. Mauris nec mauris eu
              risus varius convallis. Aliquam ut varius turpis, sed condimentum sem.
              Mauris nec mauris eu risus varius convallis. Aliquam ut varius turpis,
              sed condimentum sem.
            </p>
            <img :src="close" alt="">

        </div>
    </div>
</template>

<script>

import close from "../assets/close.png"

export default {
    data(){
        return{
            close: close
        }
    },

    props: {
        testingClicked: {
            type: Function
        }
    },

    methods: {
        showFaq(){
            this.$emit('onShowFaqClicked')
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
        z-index: 50;
      
    }
    .inner{
        z-index: 100;
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
        overflow-y: scroll;
    }

    h1{

        text-align: center;
        margin: 0px;
    }



    img{
        width: 20px;
        height: 20px;

        position: absolute;
        top: 20px;
        right: 20px;
    }


</style>