<template>
    <div id="banner">
        <h1>Easy Story</h1>
    </div>
</template>

<script>
export default{
    name: 'Banner'
}
</script>

<style scoped lang="scss">
#banner{
    background-image: url("../assets/storage.jpg");
    background-size: cover;
    height: 20rem;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: flex-start;

    h1{
        color: #fff;
        text-align: center;
        font-size: 6rem;
        background-color: #222;
        padding: 2rem 4rem;
    }
}
</style>