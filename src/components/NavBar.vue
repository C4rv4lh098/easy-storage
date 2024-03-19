<template>
    <div class="nav">
        <router-link to="/" id="logo">
            <img :src="logo" :alt="alt" id="logo">
        </router-link>
        <router-link to="/">Adicionar</router-link>
        <router-link to="/list">Visualizar Estoque</router-link>
    </div>
</template>

<script>
export default {
    name: 'NavBar',
    props: ["logo", "alt"]
}
</script>

<style scoped>
.nav {
    display: flex;
    flex-direction: row;
    height: 6rem;
    width: 100%;
    align-items: center;
    justify-content: flex-start;
    background-color: #222;

    font-size: 2rem;
}

a {
    text-decoration: none;
    color: #fff;
    margin-left: 3.5rem;
    transition: .5s;
}

a:hover {
    color: darkcyan;
}

#logo {
    height: 5.6rem;
    margin-right: 70rem;
}
</style>