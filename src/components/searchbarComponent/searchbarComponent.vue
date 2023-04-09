<template>
  <div class="search-bar">
    <input type="text" v-model="query" placeholder="Szukaj..." />
    <button @click="search">Szukaj</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      query: "",
    };
  },
  methods: {
    search() {
      // Do something with the search query
      console.log("Search query:", this.query);
    },
  },
};
</script>

<style>
.search-bar {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 40px;
  width: 100%;
  max-width: 500px;
  background-color: #fff;
  border-radius: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.search-bar input[type="text"] {
  height: 100%;
  flex: 1;
  padding: 0 10px;
  border: none;
  border-radius: 20px 0 0 20px;
}

.search-bar button {
  height: 100%;
  padding: 0 20px;
  border: none;
  border-radius: 0 20px 20px 0;
  background-color: #007bff;
  color: #fff;
  font-weight: bold;
  cursor: pointer;
}
</style>
