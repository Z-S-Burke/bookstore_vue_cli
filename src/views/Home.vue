<template>
  <div class="home">
    <Header/>
    <Bookshelf/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";
import Bookshelf from "@/components/Bookshelf.vue";

export default {
  name: "home",
  components: {
    Header,
    Bookshelf
  }
};
</script>

<style>

.logo {
  height: 200px;
  width: 200px;
}

</style>

