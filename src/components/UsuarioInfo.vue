<template>
    <div class="componente">
        <h2>As Informações de Usuário</h2>
        <p>Vários detalhes...</p>
        <p>Nome do usuário: <strong>{{ inverterNome() }}</strong></p>
        <p>Nome do usuário: <strong>{{ nome }}</strong></p>
        <button @click="reiniciarNome">Reinicilizar Nome</button>
        <button @click="reiniciarFn">Reinicilizar Nome (Callback)</button>
    </div>
</template>

<script>
export default {
    props: {
        nome: {
            type: String,
            // required: true,
            // default: function() {
            //     return Array(10).fill(0).join(':')
            // }
            default: 'Anônimo'
        },
        reiniciarFn: Function
    },
    methods: { 
        inverterNome() {
            return this.nome.split('').reverse().join('')
        },
        reiniciarNome() {
            this.nome = 'Paulo Daniel'
            this.$emit('nomeMudou', this.nome)
        }
    }

}

</script>

<style scoped>
    .componente {
        flex: 1;
        background-color: #ec485f;
        color: #fff;
    }
</style>
