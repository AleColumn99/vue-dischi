<template>

  <div id="app">

    <div v-if="!loading" class="container text-center mt-5">
  
      <div class="wrap d-flex justify-content-center align-items-center" >

        <Card
          v-for="card in cards"
          :key="card.id"
          :card="card"
        />
        
      </div>

    </div>

    <Loading title="Albums" v-else />

  </div>

</template>

<script>

import axios from 'axios';
import Card from '@/components/Card';
import Loading from '@/components/Loading';

export default {
  name: 'App',
  components: {
    Card,
    Loading
  },
  data() {
    return {
      axios,
      cards: [],
      loading: true
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then( res => {
      console.log(res.data);
      this.loading = false;
    })
    .catch( err => {
      console.log(err);
    })
  }
}

</script>

<style lang="scss">

@import '@/assets/style/general';

</style>
