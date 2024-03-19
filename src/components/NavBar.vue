<template>
    <div class="nav">
        <router-link to="/" id="logo">logoAqui
        </router-link>
        <router-link to="/">Adicionar</router-link>
        <router-link to="/list">Visualizar Estoque</router-link>
    </div>
</template>

<script>
export default{
    name: 'NavBar'
}
</script>

<style scoped>
.nav{
    display: flex;
    flex-direction: row;
    height: 6rem;
    width: 100%;
    align-items: center;
    justify-content: start;
    background-color: #222;

    font-size: 2rem;

    a{
        text-decoration: none;
        color: #fff;
        margin-left: 3.5rem;
        transition: .5s;
    }

    a:hover{
        color: darkcyan;
    }

    #logo{
        margin-right: 140rem;
    }
}
</style>