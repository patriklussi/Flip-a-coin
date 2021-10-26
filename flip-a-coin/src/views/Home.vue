<template>
  <div class="home">
    <Header/>
    <coinflip />
  </div>
</template>

<script>
// @ is an alias to /src
import coinflip from '@/components/coinflip.vue'
import Header from "@/components/Header.vue"

export default {
  name: 'Home',
  components: {
    coinflip,
    Header,
  }
}
</script>
