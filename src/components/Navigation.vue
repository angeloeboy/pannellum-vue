<template>
    <nav>
        <button @click="showVid">Show Video</button>
        <button @click="showQuiz">Quiz</button>
        <button @click="showFaq">FAQ</button>
    </nav>
</template>


<script>
export default {
    props: {
        testingClicked: {
            type: Function
        }
    },

    methods: {
        showVid(){
            this.$emit('onShowVidClicked')
        },

        showFaq(){
            this.$emit('onShowFaqClicked')
            console.log("clicked")
        },

        showQuiz(){
            this.$emit('onShowQuizClicked')
            
        }


    }
}
</script>

<style scoped>

nav{
    position: absolute;
    bottom: 0;
    width: 100vw;
    padding: 20px;
    z-index: 999;
    box-sizing: border-box;
    background-color: black;
    display: flex;
    justify-content: center;
}   
button{
    background-color: transparent;
    padding: 10px 20px;
    color: white;
    border: 1px solid white;
    margin: 10px;
    width: 200px;
}

        
</style>