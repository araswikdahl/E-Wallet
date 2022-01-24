<template>
  <div>
      <h1>{{data.cardName}}</h1>
      <h1>{{data.cardNumber}}</h1>
  </div>
</template>

<script>
export default {
    data(){
        return{
         list: []
        
        }
    },
    props:['data'],
    methods:{

funktion(){
this.list.push(this.data)
console.log('hej')
}
    },
       mounted(){ 
    this.funktion()
  }


}
</script>

<style>

</style>