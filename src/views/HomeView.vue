<template>
  <div class="home">
    <HeaderComponent/>
    <CardComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import CardComponent from '../components/CardComponent.vue';
import HeaderComponent from '../components/HeaderComponent.vue';

export default {
  name: 'HomeView',
  components: {
    HeaderComponent,
    CardComponent
  }
}
</script>

<style>  
  .header {
    background: #000;
    height: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>