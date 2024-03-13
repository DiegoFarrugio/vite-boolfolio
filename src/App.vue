<script>
//Importazione componente
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';


export default{
    data(){
        return{
            message: 'hello'
        }
    },

    components: {
      HeaderComponent,
      MainComponent,
      FooterComponent,
    }
};
</script>


<template>

  <HeaderComponent/>
  <MainComponent/>
  <FooterComponent/>

</template>



<style scoped>


</style>
