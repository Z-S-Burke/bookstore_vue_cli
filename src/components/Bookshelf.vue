<template>
  <div class="CONTENT d-flex">
    <div class="search_spacer mb-5">
      <div class="d-flex flex-column">
        <label for="search_bar" class="search_placeholder pr-5">Search by title, keyword... &#10549;</label>
        <div>
          <input
            type="text"
            class="search_bar pb-3 border-bottom border-dark"
            v-model="search"
            id="search_bar"
          >
        </div>
      </div>
    </div>
    <div class="mt-5" v-for="book of filteredBooks" :key="book.id">
      <Book :oneBook="book"/>
    </div>
  </div>
</template>

<script>
import Book from "@/components/Book.vue";
export default {
  name: "Bookshelf",
  components: {
    Book
  },
  data() {
    return {
      bookURL: "https://api.myjson.com/bins/udbm5",
      books: [],
      search: " ",
      showModal: false
    };
  },
  methods: {
    getData(bookURL) {
      fetch(bookURL, {
        headers: {
          "Content-Type": "application/json"
        },
        mode: "cors"
      })
        .then(response => {
          return response.json();
        })
        .then(data => {
          this.books = data.books;
        })
        .catch(err => {
          throw err;
        });
    }
  },
  mounted() {
    this.getData(this.bookURL);
  },
  computed: {
    filteredBooks() {
      return this.books.filter(book => {
        return (
          book.titulo.toLowerCase().includes(this.search.toLowerCase()) ||
          book.descripcion.toLowerCase().includes(this.search.toLowerCase())
        );
      });
    }
  }
};
</script>

<style>
.search_bar {
  height: 50px;
  width: 100%;
  border-style: hidden;
  text-align: right;
}

.search_placeholder {
  text-align-last: right;
  width: 100%;
}

.search_spacer {
  height: 50px;
  width: 100%;
}
</style>
