<template>
    <div>
        <div class="inner">
        <h1>Login</h1>
        <form>
            <p>Username</p>
            <input type="text" v-model="userName">
            <p>Password</p>

            <input type="password" v-model="passWord">
            <button @click="login">Login</button>
        </form>
        </div>


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

div{
    position: relative;
    width: 100%;
    height: 100%;

}

div.inner{
    /* position: absolute;
    top: 50%;
    left: 50%;
    height: 50%;
    padding: 10px;
    background-color: pink; */
    display: block;
    margin: 0 auto;
    width: 30%;

}

input{
    width: 100%;
    display: block;
    margin: 10px 0px;
}
button{
    background-color: black;
    color: white;
    padding: 10px 30px;
    border: 0px;
}
</style>