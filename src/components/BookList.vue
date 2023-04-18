<template>
    <div class="book-list">
      <BookItem v-for="book in books" :book="book" :key="book.id" :favourite = "book.favorite "/>
    </div>
  </template>
  
  <script>
  import BookItem from './BookItem.vue';
  
  export default {
    name: 'BookList',
    components: {
      BookItem,
    },
    props: {
      books: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
<style scoped>
.book-list {
    padding: 20px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 20px;
}

</style>
