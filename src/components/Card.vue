<template>
<div class="CardAndForm">
    <div class="card">      
        <div class="heroIconsWrapper">
            <div class="iconsWrapper">
                <img class="iconsStyle" src="../assets/wifi.svg" width="50px">
                <img class="iconsStyle" src="../assets/chip.svg" width="50px">
            </div>
                 <img class="iconsStyle" src="../assets/Bitcoin logo.png" width="40px">
        </div>
        <div class="cardNumberWrapper">
            <h3>{{user.cardNumber}}</h3>
        </div>
        <div class="cardTextWrapper">
            <div class="cardNameWrapper">
                <p>CARDHOLDER NAME</p>
                <div class="cardNames">
                    <p>{{user.cardName}}</p>
                </div>     
            </div>
            <div class="validWrapper">
              <p>VALID THRU</p>
              <p>{{user.valid}}</p>
            </div>           
        </div>   
    </div>
   
</div>  
</template>

<script>
export default {
        props: ['user','objectdata'],
    methods:{
    
    },
   

}
</script>

<style>
.card{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 380px;
    height: 240px;
    background-color: #D0D0D0;
    border-radius: 8px;
    padding: 10px;
    box-shadow:  0px 0px 32px rgba(0, 0, 0, 0.1);
       
}
.heroIconsWrapper{
    display: flex;
    justify-content: space-between;
 
}
.iconsWrapper{
    display: flex;
    flex-direction: column;
}
.cardNumberWrapper{
    font-size: 24px;
    text-align: center;

}
.cardTextWrapper{
    display: flex;
    justify-content: space-between;
}
.cardNameWrapper p{
    padding: 5px;
}
.cardNames{
    display: flex;
}
.cardNames p{
    padding: 5px;
}
.validWrapper p{
padding: 5px;
}
.iconsStyle{
    width: 40px;
    height: 50px;
}

</style>