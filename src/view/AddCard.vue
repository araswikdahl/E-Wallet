<template>
  <article class="home">
      <header class="headings">
          <div class="addcardHeading">
            <h1>ADD A  NEW BANK CARD</h1>
            <p class="card-status">NEW CARD</p>
          </div>   
      </header>
      <Form @sendToAddCard="sendPayload"/>
  </article>
</template>

<script>

import Form from '../components/Form.vue'

export default {
    data(){
        return{
            objectdata:[],
        }
    },
    components:{
         Form
    },
    methods:{
        sendPayload(formdata){
            this.objectdata=formdata
           this.$emit('sendToApp', this.objectdata)
        }
    }

}
</script>

<style>


</style>