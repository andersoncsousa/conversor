<template>
    <div id="app">
        <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
        <!-- <HelloWorld msg="Welcome Caiqueira"/> -->
        <h1 class="text-principal">Conversor de Moedas</h1>
        <div class="linha">
            <conversor moedaA="USD" moedaB="BRL"/>
            <conversor moedaA="BRL" moedaB="USD"/>
        </div>
        <div class="linha">
            <conversor moedaA="CAD" moedaB="BRL"/>
            <conversor moedaA="BRL" moedaB="CAD"/>
        </div>
        <div class="linha">
            <conversor moedaA="EUR" moedaB="BRL"/>
            <conversor moedaA="BRL" moedaB="EUR"/>
        </div>
    </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Conversor from "./components/conversor.vue"
export default {
    name: 'app',
    components: {
    // HelloWorld
    Conversor
    }
}
</script>

<style>
#app {
    margin: 0 auto;
    max-width: 900px;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: cornflowerblue;/*#6495ed*/
    margin-top: 60px;
}
.linha{
    margin-top: 40px;
    display: flex;
    justify-content: space-between;
}
.text-principal{
    text-align: center;
}
</style>
