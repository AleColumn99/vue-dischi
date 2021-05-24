<template>

  <div class="col-sm-6 col-md-4 col-lg-3 mb-5">
    <img :src="card.poster" alt="card.name">
    <h3>{{ card.title }}</h3>
    <h5>{{ card.author }}</h5>
    <h5>{{ card.year }}</h5>
  </div>
  
</template>

<script>
export default {
  name: 'Card',
  props: {
    card: Object
  }
}
</script>

<style>



</style>