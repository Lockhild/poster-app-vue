<template>
  <v-app>
    <Header/> 
    <Main/>
    <Footer/>
  </v-app>
</template>

<script>
import Header from './components/Header';
import Main from './components/Main';
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
  data: () => ({
    //
  }),
};
</script>

<style>
  .label {
    font-size: 16px;
  }
</style>