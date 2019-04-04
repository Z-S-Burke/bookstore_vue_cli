<template>
  <div id="app">
    <Header/>
    <div id="nav">
      <router-link to="/">Bookshelf</router-link> |
      <router-link to="/about">Home</router-link>
    </div>
    <router-view/>
    <Footer/>
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";
import Header from "@/components/Header.vue";

export default {
  name: "footer",
  components: {
    Footer,
    Header
  }
};
</script> 

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
/* 
.grid-container {
    display: grid;
    grid-template-columns: 0.2fr 1.2fr 1.2fr 0.2fr;
    grid-template-rows: 0.2fr 1.4fr 1.4fr 0.2fr;
} */

.CONTENT {
  grid-area: 2 / 2 / 4 / 4;
  display: flex;
  flex-flow: wrap;
  justify-content: space-between;
}

.HEADER {
  grid-area: 1 / 1 / 2 / 5;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-bottom: 3%;
}

.FOOTER {
  grid-area: 4 / 1 / 5 / 5;
  display: flex;
  justify-content: center;
  margin-top: 5%;
}
</style>
