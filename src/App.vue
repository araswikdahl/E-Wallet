<template>
  <div id="app">
    <Home @changeView="change" v-if="currentView == 'home'" v-bind:listdata="listdata"/>
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
      listdata: []
    }
  },
  methods:{
    AddCardPayload(u){
       this.listdata.push(u)
       console.log(u)
       this.currentView = 'home'   
    },
    change(){
      this.currentView = 'addCard'
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
