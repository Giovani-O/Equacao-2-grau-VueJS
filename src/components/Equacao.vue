<template>
    <div class="equacao">
        <h2>Equação de segundo grau</h2>
        <input type="text" v-model="a" placeholder="a" />
        <input type="text" v-model="b" placeholder="b" />
        <input type="text" v-model="c" placeholder="c" /><br>
        <input type="button" value="Calcular" v-on:click="calcular">
        <h2>{{ resultado }}</h2>
    </div>
</template>

<script>
    export default{
        name: "Equacao",
        a: 0,
        b: 0,
        c: 0,
        data() {
            return {
                resultado: "Resultado: "
            }
        },
        methods: {
            calcular() {
                let delta = (Math.pow(this.b, 2) - 4 * this.a * this.c);
                let xAdicao = ((-this.b + Math.sqrt(delta)) / (2 * this.a)).toFixed(2);
                let xSubtracao= ((-this.b - Math.sqrt(delta)) / (2 * this.a)).toFixed(2);
                
                this.resultado = "x1: " + xAdicao + " x2: " + xSubtracao + " delta: " + delta;
            }
        }
    }
</script>

<style scoped>
    .equacao {
        margin: 0 auto;
        padding: 5px;
        max-width: 500px;
        background-color: #eee;
        border-radius: 5px;
        box-shadow: 1px 1px 10px #111;
    }

    .equacao input {
        margin: 5px;
    }
</style>