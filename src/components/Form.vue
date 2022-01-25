<template>
  <div class="registerForm">

      <Card  v-bind:user="user"/>

    <form @submit.prevent="">
      <label for="cardNumber">CARD NUMBER</label>
      <input class="cardNumber" v-model="user.cardNumber" type="number">

      <label for="cardHolderName">CARDHOLDER NAME</label>
      <input class="cardHolderName" v-model="user.cardName" type="text">

      <div class="formValidWrapper">
        <div class="formvalidCcvWrapp">
          <label for="expireMonth">MONTH</label>
          <select v-model="user.expireMonth" name="MONTH" id="expireMonth">
            <option v-for="month in 12" :key="month">{{month}}</option>
          </select>
    
        </div>
        <div class="formvalidCcvWrapp">
             <label for="expireYear">YEAR</label>
          <select v-model="user.expireYear" name="MONTH" id="expireYear">
            <option>{{22}}</option>
            <option>{{23}}</option>
            <option>{{24}}</option>
            <option>{{25}}</option>
          </select>
          
        </div>
      </div>
      <div class="vendorWrapp">
          <label for="vendor">VENDOR</label>
        <select v-model="user.vendor" name="vendor">
            <option value="ninja">Ninja</option>
            <option value="bitcoin">Bitcoin</option>
            <option value="evil">Evil</option>
            <option value="blockchain">Blockchain</option>
        </select>
      </div>    
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
             expireMonth:'',
             expireYear:'',
             activcard:false,
        }         
    }    
  },
  components: {
         Card
    },
  methods:{
      createList(){
          this.$emit('sendToAddCard',{...this.user})
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
  margin: 10px 0px
}
.formvalidCcvWrapp{
  display: flex;
  flex-direction: column;
}
.formvalidCcvWrapp select{
  width: 180px;
}
.vendorWrapp{
  display: flex;
  flex-direction: column;
}
.btnForm{
  background-color: black;
  color: white;
  margin-top: 20px;
}
select option{
  background-color: blue;
 width: 50px;
 padding: 100px;
}

</style>