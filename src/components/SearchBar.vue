<template>
    <div class="search-bar">
      <input type="text" placeholder="Search book" v-model="searchQuery">
      <button class="clear" @click="clearSearch">Clear</button>
      <button class="add" @click="addBook">Add book</button>
    </div>
  </template>
  
  <script>
   export default {
    name: 'SearchBar.vue',
    data() {
    return {
      searchQuery: ''
    }
  }
    
  }
 
  </script>

  <style scoped>
  .search-bar {
display: flex;
justify-content: space-between;
align-items: center;
padding: 10px 20px;
background-color: #f5f5f5;
border-bottom: 1px solid #e5e5e5;
}
.search-bar input {
width: 100%;
padding: 10px;
border: 1px solid #e5e5e5;
border-radius: 4px;
outline: none;
}
.search-bar button {
padding: 10px;
border: 1px solid #e5e5e5;
border-radius: 4px;
outline: none;
cursor: pointer;
min-width: 100px;
}
.search-bar .clear {
margin-right: 10px;
}
.search-bar .add {
background-color: #4caf50;
color: #fff;
}


    </style>