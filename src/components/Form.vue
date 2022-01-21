<template>
  <div class="registerForm">
    <form action="">
      <label for="cardNumber">CARD NUMBER</label>
      <input class="cardNumber" @keyup="testFunktion" v-model="card.cardNumber" type="number">

      <label for="cardHolderName">CARDHOLDER NAME</label>
      <input class="cardHolderName" @keyup="testFunktion" v-model="card.cardName" type="text">
      <div class="formValidWrapper">
        <div class="formvalidCcvWrapp">
          <label for="valid">VALID THRU</label>
          <input class="valid" type="text">
        </div>
        <div class="formvalidCcvWrapp">
          <label for="ccv">CCV</label>
          <input class="ccv" @keyup="testFunktion" v-model="card.ccv" type="text">
        </div>
      </div>
      <label for="vendor">VENDOR</label>
      <input class="vendor" type="text">
      <button class="btn btnForm">ADD CARD</button>
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
             ccv:'',
        }
      
    }
  },
  methods:{
      testFunktion(){
          this.$emit('hej', this.card)
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
input{
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