<template>
    <div>
        <h1>Hola Mundo</h1>

        <p v-on:click="myClick" >{{ valor }}</p>

        <!-- <button @click="myClick">Dame un click</button> -->
        <button @click="contador(1)">+1</button>
        <button @click="contador(-1)">-1</button>
        <br>
        <button @click="valor++">+1</button>
        <button @click="valor--">-1</button>
    </div>
</template>

<style scoped>
 h1 {
     color: red
 }
</style>

<script>
export default {
    name:"otro",
    data(){
        return {
            valor: 0
        }
    },
    methods: {
        myClick: function(){
            this.valor='andres'

            alert("NO!!!")
        },
        contador(v){
            this.valor += v
        }
    }
}
</script>