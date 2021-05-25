<template>

  <div class="wrapper col-sm-6 col-md-3 col-lg-2 mb-5">
    <img :src="card.poster" alt="card.title">
    <h5>{{ card.title }}</h5>
    <p>{{ card.author }}</p>
    <p>{{ card.year }}</p>
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
   min-width: 250px;
   min-height: 400px;
   margin: 10px;
   background-color: #2E3A46;
   img {
     margin: 20px;
     width: 200px;
     height: 200px;
   }
   h5 {
     min-height: 60px;
     margin: 10px;
     color: #FFFFFF;
     text-transform: uppercase;
   }
   p {
     color: #797E7F;
   }
 }

</style>