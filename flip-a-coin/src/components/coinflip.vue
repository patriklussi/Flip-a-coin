<template>
 <div class="wrapper">
   <article v-if="toggle" class="choiceContainer">
     <h2>Choose either heads or tails</h2>
     <button value=1 @click="selectHead($event)">Heads</button>
     <button value =2 @click="selectHead($event)"  >Tails</button>
   </article>
   <article v-else class="flipContainer">
     <p>Your pick: {{selectedSide}}</p>
    <button>Flip a coin</button>
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
        coinflipText:" ",
        selectedSide :" ",
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
      console.log(value);
     if(value === "1") {
      console.log("yo");
     } else if(value === "2"){
      console.log("yo2");
     }

      console.log(this.selectedSide);

    },

   
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
