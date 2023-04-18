<template>
    <div class="filter-bar">
      <div class="filter-bar__select">
        <label for="order-select">Ordenar por:</label>
        <select id="order-select" v-model="orderBy" @change="updateFilter">
          <option value="title">Título</option>
          <option value="author">Autor</option>
          <option value="year">Año</option>
          <option value="rating">Valoración</option>
        </select>

      </div>
      <div class="filter-bar__select">
        <label for="sort-select">Orden:</label>
        <select id="sort-select" v-model="sortOrder" @change="updateFilter">
          <option value="asc">Ascendente</option>
          <option value="desc">Descendente</option>
        </select>
      </div>
      <div class="filter-bar__check">
        <label>
          <input type="checkbox" v-model="showFavorites" @change="updateFilter">
          Mostrar solo favoritos
        </label>
      </div>
    </div>
  </template>
  
  <script>

  export default {
    name: 'FilterBar.vue',
    data() {
      return {
        orderBy: null,
        sortOrder: null,
        showFavorites: false 
      }
  }
}
  </script>
  

  <style scoped>
    .filter-bar {
    display: flex;
    align-items: center;
    padding: 20px;
    background-color: #f5f5f5;
    border-bottom: 1px solid #ccc;
    }
    .filter-bar__select {
    display: flex;
    align-items: center;
    margin-right: 20px;
    }
    .filter-bar__select label {
    margin-right: 10px;
    }
    .filter-bar__select select {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    outline: none;
    }
    .filter-bar__check {
    display: flex;
    align-items: center;
    }
    .filter-bar__check input {
    margin-right: 10px;
    }
    .filter-bar__check label {
    cursor: pointer;
    }
    </style>