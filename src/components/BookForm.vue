<template>
     
            <div class="book-form">
  <form class="book-form__form">
    <div class="book-form__form-group">
      <label for="id">Identificador del libro:</label>
      <input type="text" id="id" name="id" required>
    </div>
    <div class="book-form__form-group">
      <label for="title">Título del libro:</label>
      <input type="text" id="title" name="title" required>
    </div>
    <div class="book-form__form-group">
      <label for="author">Autor del libro:</label>
      <input type="text" id="author" name="author" required>
    </div>
    <div class="book-form__form-group">
      <label for="year">Año de publicación:</label>
      <input type="number" id="year" name="year" required>
    </div>
    <div class="book-form__form-group">
      <label for="pages">Número de páginas:</label>
      <input type="number" id="pages" name="pages" required>
    </div>
    <div class="book-form__form-group">
      <label for="cover">URL de la imagen portada del libro:</label>
      <input type="url" id="cover" name="cover" required>
    </div>
    <div class="book-form__form-group">
      <label for="genre">Género del libro:</label>
      <input type="text" id="genre" name="genre" required>
    </div>
    <div class="book-form__form-group">
      <label for="description">Texto de sinopsis o descripción del libro:</label>
      <textarea id="description" name="description" required></textarea>
    </div>
    <div class="book-form__form-group">
      <label for="editorial">Nombre de la editorial del libro:</label>
      <input type="text" id="editorial" name="editorial" required>
    </div>
    <div class="book-form__form-group">
      <label for="language">Idioma del libro:</label>
      <input type="text" id="language" name="language" required>
    </div>

    <div class="book-form__form-group">
        <label for="isbn">ISBN:</label>
        <input id="isbn" type="text" v-model="book.isbn" required>
      </div>
      <div class="book-form__form-group">
        <label for="price">Precio:</label>
        <input id="price" type="number" v-model="book.price" required>
      </div>
      <div class="book-form__form-group">
        <label for="stock">Cantidad en stock:</label>
        <input id="stock" type="number" v-model="book.stock" required>
      </div>
      <div class="book-form__form-group">
        <label for="favorite">¿Libro favorito?</label>
        <input id="favorite" type="checkbox" v-model="book.favorite">
      </div>
      <div class="book-form__form-group">
        <label for="rating">Rating</label>
        <input type="number" id="rating" v-model="book.rating" min="1" max="5" required>
      </div>
      <div class="book-form__form-group">
        <label for="personalNote">Personal Note</label>
        <input type="text" id="personalNote" v-model="book.personalNote">
      </div>

      <div class="book-form__submit">
        <button type="submit" class="book-form__submit">Submit</button>
      </div>
        </form>
     

        </div>


  </template>
  
  <script>
  export default {
    name: 'BookFormvue',
    props: {
      book: {
        type: Object,
        required: true
      }
    },
    
  }
  </script>

  <style scoped>

.book-form__form {
display: flex;
flex-wrap: wrap;
}
.book-form__form-group {
margin-bottom: 20px;
width: 50%;
display: flex;
flex-direction: column;
}
.book-form__form-group label {
display: block;
margin-bottom: 10px;
text-align: left;
font-size: 14px;
}

.book-form__form-group input,
.book-form__form-group textarea {
width: 80%;
padding: 10px;
border: 1px solid #e5e5e5;
border-radius: 4px;
outline: none;
text-align: left;
}
.book-form__form-group input:focus,
.book-form__form-group textarea:focus {
border-color: #000;
}
.book-form__form-group textarea {
height: 100px;
}
.book-form__submit {
padding: 10px;
border: 1px solid #e5e5e5;
border-radius: 4px;
outline: none;
cursor: pointer;
min-width: 100px;
background-color: #4caf50;
color: #fff;
}
.book-form__submit:hover {
background-color: #43a047;
}

  </style>