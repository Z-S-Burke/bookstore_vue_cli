<template>
  <div id="app">
    <div class="HEADER d-flex">
      <div class="d-flex justify-content-between align-items-center">
        <img class="logo mt-3 ml-3" alt="bookstore logo" src="../assets/tetris-T-block-plain.png">
        <div class="d-flex justify-content-center align-items-center">
          <p class="title_text display-4 px-3">L I B R O</p>
          <p class="title_text display-4 px-3">&#124;</p>
          <p class="title_text display-4 text_mirror px-3">L I B R O</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title_text {
  font-family: monospace !important;
  text-align: center;
}

.text_mirror {
  transform: scale(-1, 1);
}
</style>
