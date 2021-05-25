<template>

  <div class="header d-flex">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/71/Spotify.png" alt="spotify-logo">
    <!-- <div class="slider-menu">
      <div class="menu-voice">
        <h3>
          Genres
        </h3>
      </div>
      <div class="menu-list">
        <ul>
          <li
            v-for="(card, index) in cards"
            :key="index"
            :genre="card.genre"
          >
            {{ card.genre }}
          </li>
        </ul>
      </div>
    </div> -->
  </div>
  
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style>

.header {
  height: 50px;
  background-color: #2E3A46;
}
img {
  height: 40px;
  margin: 5px 20px;
}

</style>