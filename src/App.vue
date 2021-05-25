<template>

  <div id="app">

    <Header />

      <div class="main-wrap">

        <!-- <Search @searchAlbum="search"/> -->

        <div v-if="!loading" class="d-flex container text-center mt-5">
      
          <div class="row justify-content-center align-items-center">

            <Card
              v-for="(card, index) in cards"
              :key="index"
              :card="card"
            />
            
          </div>

        </div>

        <Loading title="Albums" v-else />

      </div>

  </div>

</template>

<script>

import axios from 'axios';
import Card from '@/components/Card';
import Loading from '@/components/Loading';
import Header from '@/components/Header';
/* import Search from '@/components/Search'; */

export default {

  name: 'App',

  data() {
    return {
      axios,
      cards: Array,
      genres: Array,
      loading: true,
      textToSearch: ''
    }
  },

  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then(res => {
        this.cards = res.data.response;
        this.loading = false;
        console.log(res.data);
      })
      .catch(err => {
        console.log(err);
      })
  },

  components: {
    Card,
    Loading,
    Header,
    /* Search */
  },

  computed: {
    /* filteredCards() {
      let cleanArr = this.cards.filter(item => item.name !=undefined);
      if (this.textToSearch === '') {
        return cleanArr;
      }
      return this.cards.filter(item => item.name.toLowerCase().includes(this.textToSearch.toLowerCase()))
    } */
  },

  methods: {
    /* search(text) {
      this.textToSearch = text;
    } */
  },

}

</script>

<style lang="scss">

@import '@/assets/style/general';

.main-wrap {
  width: 80%;
   max-width: 1800px;
   margin: auto;
   overflow: auto;
}

</style>
