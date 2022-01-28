<template>
<article class="home">
    <header class="headings">
        <div>
            <h1>E-WALLET</h1>
            <p class="card-status">ACTIVE CARD</p>
        </div>     
    </header>
    <div class="placeholderCard">

        <Card v-if="activeCard" :user="activeCard"/> 

    </div>
    <main class="gridforcards">
        <Card v-for="object in listdata" 
        :key="object.cardNumber"
        @click="activeCard=object"
        :user="object"
        />
    </main>
    <nav class="btnWrapper">
        <button @click="viewChanger" class="btn">ADD A NEW CARD</button>
    </nav>   
</article>
</template>

<script>

import Card from '../components/Card.vue'

export default {
    data(){
        return{
        activeCard:null
        }
    },
    components:{
        Card
    },
    props:["listdata"],
    methods:{
        viewChanger(){
            this.$emit('changeView')

       
        }
        
    }

}
</script>


<style>

.home{
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: 100%;
    grid-gap: 20px;
    justify-content: space-between;
    align-items: center;
    background-color: rgb(248, 248, 248);
    height: 100vh;
    width: 100%;
    box-sizing: border-box;
    padding: 10px;
}
.headings{
    grid-row: auto;
    align-items: center;
    font-family: sans-serif;
    text-align: center;
}
.headings h1{
    padding: 20px 45px;
}
.btn{
    padding: 20px;
    border-radius: 8px;
    background-color: white;
    font-size: 22px;
    font-weight: bold;
    border: 1px solid black;
    width: 380px;
    margin-top: 40px;
}
.btnWrapper{
    margin: auto;
}
.card-status{
    font-size: 12px;
     color: rgba(34, 34, 34, 0.6)
}
.gridforcards{
    grid-row: auto;
    display: grid;
    grid-auto-rows: 4rem ;
    margin-bottom: 40%;

}

</style>