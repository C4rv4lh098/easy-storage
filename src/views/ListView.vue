<template>
    <div class="main">
        <h1>Gerênciar Produtos: </h1>
        <Dashboard/>
    </div>
</template>

<script>
import Dashboard from "/src/components/Dashboard";
import Banner from "/src/components/Banner";

export default{
    name: 'ListView',
    components:{
        Banner,
        Dashboard
    }
}
</script>