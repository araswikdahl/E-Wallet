<template>
  <div class="home">
      <article class="headings">
        <h1>ADD A  NEW BANK CARD</h1>
        <p class="card-status">NEW CARD</p>
      </article>
      <Form @sendToAddCard="sendPayload"/>
  </div>
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

<style scoped>

</style>