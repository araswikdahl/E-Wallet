<template>
  <div class="cardList">
       <h1>cardlist</h1>
      <!-- <h1>{{objectdata.cardName}}</h1>
      <h1>{{objectdata.cardNumber}}</h1> 
      <h1>{{objectdata.valid}}</h1> 
      <h1>{{objectdata.vendor}}</h1> 
      <h1>{{objectdata.ccv}}</h1>  -->
       <!-- <Card v-bind:user="objectdata"/> -->
  </div>
 
 
</template>

<script>
// import Card from './Card.vue'

export default {
    // components:{
    //     Card
    // },
    data(){
        return{
        
        }
    },
    props:['objectdata'],
    methods:{

// funktion(){
//     for(const pi in this.listdata){
// this.objekt.push(this.pi)
// console.log('heej')
//     }

// }
//     },
//        mounted(){ 
//     this.funktion()
//   
//
 }


}
</script>

<style>
.cardList{
    width: 200px;
    height: 400px;
    background-color: aquamarine;
}

</style>