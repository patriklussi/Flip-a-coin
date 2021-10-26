<template>
 <div class="wrapper">
   <article v-if="toggle" class="choiceContainer">
     <button ref="Heads" @click="selectHead">{{heads}}</button>
     <button  @click="selectTails">{{tails}}</button>
   </article>
   <article v-else class="flipContainer">
     <p>Your pick: {{selectedSide}}</p>
    <button @click="flipIt">Flip a coin</button>
    <p>{{coinflipText}}</p>
    <h2>{{winnerText}}</h2>
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
     setTimeout(()=> this.winnerText = "Fate said yes",2000)
    } else {
        setTimeout(()=> this.winnerText = "Fate said no",2000)
    }
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
