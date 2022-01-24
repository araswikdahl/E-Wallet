<template>
  <div class="registerForm">

      <Card  v-bind:user="user"/>

    <form @submit.prevent="">
      <label for="cardNumber">CARD NUMBER</label>
      <input class="cardNumber" @keyup="eventFunktion" v-model="user.cardNumber" type="number">

      <label for="cardHolderName">CARDHOLDER NAME</label>
      <input class="cardHolderName" @keyup="eventFunktion" v-model="user.cardName" type="text">

      <div class="formValidWrapper">
        <div class="formvalidCcvWrapp">
          <label for="valid">VALID THRU</label>
          <input class="valid" @keyup="eventFunktion" v-model="user.valid" type="number">
        </div>
        <div class="formvalidCcvWrapp">
          <label for="ccv">CCV</label>
          <input class="ccv" @keyup="eventFunktion" v-model="user.ccv" type="number">
        </div>
      </div>

      <label for="vendor">VENDOR</label>
      <select onchange="eventFunktion()" v-model="user.vendor" name="vendor">
          <option value="ninja">Ninja</option>
          <option value="bitcoin">Bitcoin</option>
          <option value="evil">Evil</option>
          <option value="blockchain">Blockchain</option>
      </select>
      <button @click="createList" class="btn btnForm" >ADD CARD</button>
    </form>
  </div>
</template>

<script>
import Card from './Card.vue'

export default {

  data(){
    return{
        user:{
             cardNumber: '',
             cardName: '',
             valid:'',
             vendor: '',
             ccv:'',
        }
           
    }


     
  },


  components: {
         Card
    },
  methods:{

      eventFunktion(){
          /* behöver jag ens en EVENT lyssnare i input???*/

      },

      createList(){
          this.$emit('sendToAddCard', this.user)
        //   let list= []
        //    list.push(this.user)
        //    console.log(list)
        //    this.lista +=list
        //  this.lista.push(this.user)

        
        //    this.$emit('skickaTillabout2', this.lista)
         
        //  this.$emit('skickaTillHome', this.card) 
      }
         
      }
  }

</script>

<style>
form{
  display: flex;
  flex-direction: column;
}
.formValidWrapper{
  display: flex;
  justify-content: space-between;
}
input, select{
  padding: 10px;
  border-radius: 8px;
  border: 1px solid black;
}
.formvalidCcvWrapp{
  display: flex;
  flex-direction: column;
}
.btnForm{
  background-color: black;
  color: white;
  margin-top: 20px;
}

</style>