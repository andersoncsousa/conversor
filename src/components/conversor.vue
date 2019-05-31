<template>
    <div class="conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" :placeholder="moedaA">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>

export default {
    name: "Conversor",
    props: ["moedaA", "moedaB"],
    data(){
        return{
            moedaA_value: "",
            moedaB_value: 0
        }
    },
    methods: {
        getUrl(currencies) {
            return [
                "http://free.currencyconverterapi.com/api/v5/convert?q=",
                currencies,
                "&compact=ultra&apiKey=af285a9098c9614181bd"
            ].join('');
        },
        converter(){
            const de_para = this.moedaA + "_" + this.moedaB
            const url = this.getUrl(de_para)//"https://free.currconv.com/api/v7/convert?q="+ de_para +"&compact=ultra&apiKey=1fd8a73e6b6b63eebe46"

            fetch(url)
                .then(res => {
                    return res.json();
                })
                .then(json => {
                    // console.log(val)
                    const cotacao = json[de_para]
                    const valor  = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                    this.moedaB_value = `${valor} ${this.moedaB}`;
                });
        }
    },
}
</script>

<style scoped>
    .conversor{
        padding: 20px;
        max-width: 300px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    }
</style>
