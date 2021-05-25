<template>

<div>
  <form class="d-flex">
    <div class="flex-grow-1 mb-5 mt-5">
      <input 
        @keyup.enter="startSearch"
        v-model.trim="stringToSearch"
        placeholder="Search albums..." 
        class="form-control" 
        type="text"
      >
    </div>
    <div>
      <button 
        @click.prevent="startSearch"
        class="btn btn-primary ms-3"
      >
        Search
      </button>
    </div>
    <div>
      <button 
        @click.prevent="resetSearch"
        class="btn btn-warning ms-3"
      >
        Reset
      </button>
    </div>
  </form>
</div>
  
</template>

<script>
export default {
  
  name: 'Search',

  data() {
    return {
      stringToSearch: ''
    }
  },

  methods: {
    startSearch() {
      this.$emit("searchAlbum", this.stringToSearch)
    },
    resetSearch() {
      this.stringToSearch = '';
      this.startSearch();
    }
  }

}
</script>

<style>

</style>