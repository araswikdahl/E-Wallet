<template>
  <div class="registerForm">
    <form @submit.prevent="createList">
      <label for="cardNumber">CARD NUMBER</label>
      <input class="cardNumber" @keyup="eventFunktion" v-model="card.cardNumber" type="number">

      <label for="cardHolderName">CARDHOLDER NAME</label>
      <input class="cardHolderName" @keyup="eventFunktion" v-model="card.cardName" type="text">

      <div class="formValidWrapper">
        <div class="formvalidCcvWrapp">
          <label for="valid">VALID THRU</label>
          <input class="valid" @keyup="eventFunktion" v-model="card.valid" type="number">
        </div>
        <div class="formvalidCcvWrapp">
          <label for="ccv">CCV</label>
          <input class="ccv" @keyup="eventFunktion" v-model="card.ccv" type="number">
        </div>
      </div>

      <label for="vendor">VENDOR</label>
      <select onchange="eventFunktion()" v-model="card.vendor" name="vendor">
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
export default {
  data(){
    return{
        card:{
             cardNumber: '',
             cardName: '',
             valid:'',
             vendor: '',
             ccv:'',
        },
        lista: [],

        
      
    }
  },
  methods:{
      eventFunktion(){
          this.$emit('skickaTillabout', this.card)
      },
      createList(){
          
           this.lista.push(this.card)
           this.$emit('skickaTillabout2', this.lista)
         
        //  this.$emit('skickaTillHome', this.card) 
      }
    //   myFunction(){
    //     this.$emit()
    //       }
         
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