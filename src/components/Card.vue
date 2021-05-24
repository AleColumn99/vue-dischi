<template>

  <div class="wrapper col-sm-6 col-md-4 col-lg-3 mb-5">
    <img :src="card.poster" alt="card.title">
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

<style lang="scss" scoped>

 .wrapper {
   width: 300px;
   margin: 20px;
   padding: 20px;
   background-color: #2E3A46;
   img {
     width: 260px;
     height: 260px;
   }
   h3 {
     text-transform: uppercase;
   }
 }

</style>