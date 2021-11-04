<template>
 <div class="wrapper">
   <article v-if="toggle" class="choiceContainer">
     <h2>Choose either heads or tails</h2>
     <button value=0 @click="selectHead($event)">Heads</button>
     <button value =1 @click="selectHead($event)"  >Tails</button>
   </article>
   <article v-else class="flipContainer">
      <TheCoin/>
     <p>Your pick: {{coinSide}}</p>
    <button @click="flipIt()">Flip a coin</button>

    <h2>{{winnerText}}</h2>
    <button v-if="buttonToggle" @click="toggleBack">Flip again</button>
   </article>

 </div>
</template>

<script>
import TheCoin from "./TheCoin.vue"
export default {
  components: {
    TheCoin
  },
  name: 'Coinflip',
  data:function(){
      return {
       // coinflipText:" ",
        selectedSide :Number,
        coinSide :String,
        toggle:true,
        buttonToggle:false,
        winnerText:"",
      }
  },
  methods: {
    selectHead(e){
     
      this.selectedSide = this.heads;
      this.toggle = false;
     const value = e.target.value;
  
     if(value === "0") {
       this.selectedSide = 0;
       this.coinSide = "Heads"
     } else if(value === "1"){
       this.selectedSide =1
        this.coinSide = "Heads"
     }

    

    },
    flipIt(){
      const value = Math.round(Math.random() < 0.5);
     if(this.selectedSide  === value) {
        this.winnerText ="Heads";
  
     } else {
       this.winnerText ="Tails";
 
     }
      
    } 

   
  },
  
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
