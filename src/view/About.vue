<template>
  <div class="home">
      <article class="headings">
        <h1>ADD A  NEW BANK CARD</h1>
        <p class="card-status">NEW CARD</p>
      </article>
      <Card v-bind:grillkorv="hej"/>
      
      <Form @skickaTillabout="funktionabout"  @addList="TheListFunktion"
      @skickaTillabout2="funktionabout2" 
      />
  </div>
</template>

<script>
import Card from '../components/Card.vue'
import Form from '../components/Form.vue'

export default {
    data(){
        return{
            hej:'',
            kommandelistan:''
        }
    },
    components:{
        Card, Form
    },
    methods:{
        funktionabout(n){
            this.hej = n;
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