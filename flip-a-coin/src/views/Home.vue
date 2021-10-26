<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <coinflip msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import coinflip from '@/components/coinflip.vue'

export default {
  name: 'Home',
  components: {
    coinflip,
  }
}
</script>
