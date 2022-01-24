<template>
  <div id="app">
    <nav>
      <a @click="currentView = 'home'">Home</a>
      <a @click="currentView = 'addCard'">AddCard</a>
    </nav>
    <Home v-if="currentView == 'home'" v-bind:data="data"/>
    <AddCard v-else-if="currentView === 'addCard'" @sendToApp="AddCardPayload" />

  </div>
</template>

<script>
import Home from './view/Home.vue'
import AddCard from './view/AddCard.vue'

export default {
  components:{
    Home, AddCard
  },
  data(){
    return{
      currentView : 'home',
      data: ''
    }
  },
  methods:{
    AddCardPayload(u){
      this.data = u
      console.log(this.data)
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
