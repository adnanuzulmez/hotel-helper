<template>
  <div id="app">
  <Auth/>
  </div>
</template>

<script>
import Auth from './components/Auth.vue'

export default {
  name: 'App',
  components: {
    Auth
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');
*{
  font-family: 'Montserrat', sans-serif;
  margin: 0;
  padding: 0;
}

#app{
  width: 100%;
  height: 100%;
}
</style>
