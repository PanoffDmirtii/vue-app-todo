<template>
  <div id="app">
    <Header/>
    <Dashborad />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Dashborad from './components/Dashboard'
import Footer from './components/Footer'
export default {
  name: "App",
  components: {
    Header,
    Dashborad,
    Footer
  },
};
</script>

<style>
body {
  margin: 0;
  }
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
  #app {
    font-family: 'Roboto', sans-serif;
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-rows: auto 1fr auto;
    min-height: 100vh;
    overflow: hidden;
    }
</style>
