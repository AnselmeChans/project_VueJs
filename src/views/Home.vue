<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/inp.jpg">
    <helloAcceuil msg="Bienvenue sur votre page d'acceuil du TP Vue JS"/>
  </div>
</template>

<script>
// @ is an alias to /src
import helloAcceuil from '@/components/HomeHello.vue';

export default {
  name: 'home',
  components: {
    helloAcceuil,
  },
};
</script>

<style lang="stylus" scoped>
  img
    margin-top: 70px
</style>
