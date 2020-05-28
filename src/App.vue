<template>
  <div id="app">
    <div class="navigation">
      <sidebar></sidebar>
      <div class="main-bloc">
        <navbar></navbar>
        <mainblock></mainblock>
      </div>
    </div>
  </div>
</template>

<script>
import navbar from './components/Navbar'
import sidebar from './components/sidebar'
import mainblock from './components/mainblock'
export default {
  name: 'App',
  components: {
    navbar,
    sidebar,
    mainblock
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat&display=swap');

*{
  padding: 0;
  margin: 0;
  font-family: 'Montserrat', sans-serif;
}

.main-bloc{
  width: 100%;
}

.navigation{
  display: flex;
}

</style>
