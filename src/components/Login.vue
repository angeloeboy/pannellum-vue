<template>
    <div>
        <h1>Login</h1>
        <form>
            <input type="text" v-model="userName">
            <input type="password" v-model="passWord">
            <button @click="login">Login</button>
        </form>

    </div>
</template>

<script>
export default {

    data(){
        return{
            userName: "",
            passWord: ""
        }
    },

    methods: {
        login(){

            if(this.userName == "admin" && this.passWord == "admin"){
                this.$emit('login')

            }

            console.log(this.userName)
            console.log(this.passWord)
        }
    }
}
</script>


<style scoped>
button{
    background-color: black;
    color: white;
}
</style>