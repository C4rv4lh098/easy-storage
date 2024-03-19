<template>
    <div class="mensagem">
        <p>{{ msg }}</p>
    </div>
</template>

<script>
export default{
    name: 'Mensagem',
    props:{
        msg: String
    }
}
</script>

<style scoped>
.mensagem{
    color: #004085;
    background-color: #CCE5FF;
    border: .2rem solid #B8DAFF;
    border-radius: .5rem;
    padding: 1rem;
    max-width: 40rem;
    margin: 3rem auto;
}
</style>