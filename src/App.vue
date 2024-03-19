<template>
  <NavBar :logo="logo_src" :alt="app_name"/>
  <router-view />
  <Footer />
</template>


<script>
import Footer from './components/Footer.vue';
import NavBar from './components/NavBar.vue';

export default {
  components: {
    NavBar,
    Footer
  },
  data(){
    return{
      logo_src: "./assets/logo.png",
      app_name: "Easy Storage"
    }
  }
}
</script>

<style>
:root {
  font-size: 62.5%;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  background-color: #eee;
}

.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  margin: 4rem;
  min-height: 64.9rem;
  font-size: 2rem;
}

h1 {
  font-size: 5.6rem;
  margin-bottom: 1.5rem;
}
</style>