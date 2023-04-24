<template>
  <div id="app">
  <Auth v-if="isLogged == 'false' || isLogged == null || isLogged == false" @loginControl="logControl($event)"/>
  <Mainpage v-if="isLogged === 'true' || isLogged === true"/>
  </div>
</template>

<script>
import Auth from './components/Auth.vue'
import Mainpage from './components/Mainpage.vue'

export default {
  name: 'App',
  components: {
    Auth,
    Mainpage
  },
  data(){
    return {
      isLogged: false
    }
  },
  mounted(){
    
    this.isLogged = localStorage.getItem("logStatus")
    console.log(this.isLogged);
  },
  methods:{
    logControl(event){
      this.isLogged = event
      console.log(this.isLogged);
    }
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
