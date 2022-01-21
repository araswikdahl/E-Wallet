<template>
  <div id="app">
    <nav>
      <a @click="currentView = 'home'">Home</a>
      <a @click="currentView = 'about'">About</a>
    </nav>
    <Home v-if="currentView == 'home'"/>
    <About v-else-if="currentView === 'about'"/>

  </div>
</template>

<script>
import Home from './view/Home.vue'
import About from './view/About.vue'

export default {
  components:{
    Home, About
  },
  data(){
    return{
      currentView : 'home'
    }
  }

}
</script>

<style>
*{
  margin: 0;
}
h1{
 font-size: 35px;
}

</style>
