<template>
  <div class="registerForm">

      <Card  v-bind:user="user"/>

    <form @submit.prevent="createList">
      <label for="cardNumber">CARD NUMBER</label>
      <input class="cardNumber" v-model="user.cardNumber" type="number" placeholder="XXXX XXXX XXXX XXXX">

      <label for="cardHolderName">CARDHOLDER NAME</label>
      <input class="cardHolderName" v-model="user.cardName" type="text" placeholder="Firstname Lastname">

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
      <nav class="btnWrapper">
 <button class="btn btnForm" >ADD CARD</button>
      </nav>
     
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
  margin-top: 20px;
}
.formValidWrapper{
  display: flex;
  justify-content: space-between;
}
input, select{
  box-sizing: border-box;
    padding: 10px;
    border-radius: 8px;
    border: 1px solid black;
    margin: 10px 0px;
    font-size: 1.2rem;
    width: 100%;
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
        border-radius: 0.4rem;
        padding: 0.8rem;
        border: 1px solid black;
        background-color: rgb(158, 158, 158);
        color: white;    
    }

</style>