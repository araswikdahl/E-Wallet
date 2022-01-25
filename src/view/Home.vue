<template>
<div class="home">
    <article class="headings">
        <h1>E-WALLET</h1>
        <p class="card-status">ACTIVE CARD</p>
    </article>
      <div class="gridforcards">
          <Card v-for="object in listdata" 
      :key="object.cardNumber"
      :user="object"/>

      </div>


<button class="btn">ADD A NEW CARD</button>
</div>
  
</template>

<script>

import Card from '../components/Card.vue'

export default {
    components:{
        Card
    },
    props:["listdata"]

}
</script>


<style>

.home{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    background-color: rgb(248, 248, 248);
    height: 100vh;
    width: 100%;
    box-sizing: border-box;
    padding: 10px;
}
.headings{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    font-family: sans-serif;
    width: 60%;
    text-align: center;
}
.headings h1{
    padding: 30px 0px;
}
.btn{
    padding: 20px;
    border-radius: 8px;
    background-color: white;
    font-size: 22px;
    font-weight: bold;
    border: 1px solid black;
    width: 380px;

}
.card-status{
    font-size: 12px;
     color: rgba(34, 34, 34, 0.6)
}
.gridforcards{
    display: grid;
    grid-auto-rows: 4rem ;

}

</style>