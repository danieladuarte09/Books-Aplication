
<script>
import BookItem from './components/BookItem.vue';
import BookList from './components/BookList.vue';
import FilterBarVue from './components/FilterBar.vue';
import ModalLayerVue from './components/ModalLayer.vue';
import SearchBarVue from './components/SearchBar.vue';
import BookFormvue from './components/BookForm.vue';

export default {
  name: 'App',
  components: {
    BookItem,
    BookList,
    FilterBarVue,
    ModalLayerVue,
    SearchBarVue,
    BookFormvue,
  },
  data() {
    return {
      showModal: false,
      books: [
        { 
          id: 12345,
          title: 'The Lord of the rings',
          author: 'K.R.R Tolkien',
          year: '1954',
          pages: '1216',
          cover:  'https://m.media-amazon.com/images/I/71VjmMcE-rL.jpg',
          genre: 'Fantasy',
          description: 'The future of civilization rests in the fate of the One Ring, which has been lost for centuries. Powerful forces are unrelenting in their search for it. But fate has placed it in the hands of a young Hobbit named Frodo Baggins (Elijah Wood), who inherits the Ring and steps into legend. A daunting task lies ahead for Frodo when he becomes the Ringbearer - to destroy the One Ring in the fires of Mount Doom where it was forged.',
          editorial: 'Allen  & Unwin',
          language: 'English',
          isbn:  '978-0-261-10342-6',//identificador ISBN
          price: '22.95',
          stock: '10',
          favorite: true,
          rating: '5/5',//Valoración numérica del libro: de 1 a 5 (estrellas)
          personalNote: 'This is my favorite book'
        },
        { 
          
          id: 12365,
          title: "Cien años de soledad",
          author: "Gabriel García Márquez",
          year: '1967',
          pages: '471',
          cover:  'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSRdmfipQzqdkM187aS7BPq-VGfOxntCxWOIli--uJ6xc0v9DywteNqKzSC_2e0vu96lzk&usqp=CAU',
          genre: 'Novel, Fantasy',
          description: 'One Hundred Years of Solitude,is a 1967 novel by Colombian author Gabriel García Márquez that tells the multi-generational story of the Buendía family, whose patriarch, José Arcadio Buendía, founded the fictitious town of Macondo. ',
          editorial: 'Editorial Sudamericana',
          language: 'spanish',
          isbn:  ' 978-84-9759-220-8',//identificador ISBN
          price: '19.99',
          stock: '6',
          favorite: true,
          rating: '4/5',//Valoración numérica del libro: de 1 a 5 (estrellas)
          personalNote: 'It is an inspirational book'
          
        },
        { 
          
          id: 12367,
          title: "Eat, Pray, Love",
          author: "Elizabeth Gilbert",
          year: '2006',
          pages: '352',
          cover:  'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTvB3uXxBbxzJGcqExUHXHk41YARLwPpg2E8JYs2p_V0EYstaCYCO8aAIWRtlmh5rpO81w&usqp=CAU',
          genre: 'Memoir, Biography',
          description: 'One Womans Search for Everything Across Italy, India and Indonesia' ,
          editorial: 'Penguin',
          language: 'english',
          isbn:  ' 9780143113997',//identificador ISBN
          price: '10.50',
          stock: '20',
          favorite: false,
          rating: '3/5',//Valoración numérica del libro: de 1 a 5 (estrellas)
          personalNote: 'Good book if you are looking for self discovery'
          
        },
        { 
          
          id: 12477,
          title: "Emotional Intelligence",
          author:  'Daniel Goleman',
          year: '1995',
          pages: '352',
          cover:  'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT9UnHWhosZ3geP0rB8hPEHiU0Hr1BfJxpZ9A&usqp=CAU',
          genre: 'Self-help book',
          description: 'In this book, Goleman posits that emotional intelligence is as important as IQ for success, including in academic, professional, social, and interpersonal aspects of ones life.' ,
          editorial: 'Bantam Books',
          language: 'english',
          isbn:  '978-0553383713',//identificador ISBN
          price: '25.50',
          stock: '6',
          favorite: true,
          rating: '5/5',//Valoración numérica del libro: de 1 a 5 (estrellas)
          personalNote: 'It gives you the opportunity to see how the brain works sometimes'
          
        }
        
      ]
    };
  },
  methods: {
    closeModal() {
      this.showModal = false;
    }
  }
}
</script>

<template>

<div>
    <header class="header">
      <!-- Aquí va el logo de la uoc y título  -->
      <img src="./assets/uoc-logo.png" alt="Logo de la uoc" class="logo">
      <h1 class="title">Aplicación de libros</h1>
    </header>
    <section class="content">
      <!--Componentes SearchBar, FilterBar, BookList y ModalLayer -->
      <SearchBarVue></SearchBarVue>
      <FilterBarVue></FilterBarVue>
      <main class="main">
        <BookList :books="books"></BookList>
      </main>

      
      <ModalLayerVue :show="showModal" header="Add a new book" @close="closeModal">
      <template #body>
      <!-- Contenido del formulario para añadir libros -->
      <BookFormvue></BookFormvue>
      </template>
      </ModalLayerVue>
    

    </section>
  </div>
  

  
 
  
</template>

<style scoped>
body {
padding: 0;
margin: 0;
font-family: "Avenir", Helvetica, Arial, sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
text-align: center;
color: #2c3e50;
}
.header {
display: flex;
justify-content: space-between;
align-items: center;
padding: 0 20px;
background-color: #f5f5f5;
border-bottom: 1px solid #e5e5e5;
}
.header__left {
display: flex;
align-items: center;
}
.logo {
height: 40px;
margin-right: 10px;
}
.title {
font-size: 24px;
font-weight: 400;
}

</style>
