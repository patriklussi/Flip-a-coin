<template>
 <div class="wrapper">
   <article v-if="toggle" class="choiceContainer">
     <h2>Choose either heads or tails</h2>
     <button ref="Heads" @click="selectHead">{{heads}}</button>
     <button  @click="selectTails">{{tails}}</button>
   </article>
   <article v-else class="flipContainer">
     <p>Your pick: {{selectedSide}}</p>
    <button @click="flipIt">Flip a coin</button>
    <p>{{coinflipText}}</p>
    <h2>{{winnerText}}</h2>
    <button v-if="buttonToggle" @click="toggleBack">Flip again</button>
   </article>

 </div>
</template>

<script>
export default {
  name: 'Coinflip',
  data:function(){
      return {
        coinflipText:"",
        selectedSide :"",
        toggle:true,
        buttonToggle:false,
        heads:"Heads",
        tails:"Tails",
        winnerText:"",
      }
  },
  methods: {
    selectHead(){
      this.selectedSide = this.heads;
      this.toggle = false;
    },
    selectTails(){
    this.selectedSide = this.tails;
      this.toggle = false;
    },
    flipIt(){
      let coinflip = Math.floor(Math.random() < 0.5);
     if(coinflip ===1) {
       this.coinflipText = "Heads";
      
    } else {
        this.coinflipText = "Tails";
    }

    if(this.selectedSide === this.coinflipText) {
     setTimeout(()=> this.winnerText = "Fate has granted your request" ,2000)
     setTimeout(()=> this.buttonToggle= true,2000)
    } else {
        setTimeout(()=> this.winnerText = "Fate has denied your request",2000)
          setTimeout(()=> this.buttonToggle= true,2000)
    }
  },
  toggleBack(){
    this.buttonToggle = false;
    this.winnerText = "";
    this.coinflipText ="";
    this.selectedSide = "";
      this.toggle = true;
    
  }
}
}
</script>


<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
