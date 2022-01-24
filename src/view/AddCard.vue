<template>
  <div class="home">
      <article class="headings">
        <h1>ADD A  NEW BANK CARD</h1>
        <p class="card-status">NEW CARD</p>
      </article>
      
      <!-- <Form @skickaTillabout="funktionabout"  @addList="TheListFunktion"
      @skickaTillabout2="funktionabout2" 
      /> -->
      <Form @sendToAddCard="formPayload"/>
  </div>
</template>

<script>

import Form from '../components/Form.vue'

export default {
    data(){
        return{
            hej:[],
            kommandelistan:''
        }
    },
    components:{
         Form
    },
    methods:{
        formPayload(payload){
            this.hej=payload
           this.$emit('sendToApp', this.hej)

        },
        funktionabout(){
            // this.hej = n;
            // this.$emit('skickaTillcard', u)
        },
        funktionabout2(p){
            this.kommandelistan = p;
            console.log(this.kommandelistan)
            
        }
    }

}
</script>

<style scoped>

</style>