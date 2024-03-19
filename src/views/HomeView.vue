<template>
  <Banner/>
  <div class="main">
    <h1>Adicionar Produto</h1>
    <FormAdicionar/>
  </div>
</template>

<script>
import  FormAdicionar  from "/src/components/FormAdicionar";
import  Banner  from "/src/components/Banner";


export default {
  name: 'HomeView',
  components: {
    FormAdicionar,
    Banner
  }
}
</script>
