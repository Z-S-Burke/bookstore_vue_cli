<template>
  <div class="FOOTER footer_container d-flex justify-content-between border-top border-dark pt-5">
    <div class="d-flex align-items-center">
      <p class="title_text display-4 px-3 footer_text_special_mirror">O R B I L</p>
      <p class="title_text display-4 px-3">&#124;</p>
      <p class="title_text display-4 px-3 footer_text_special_mirror">L I B R O</p>
    </div>
    <img class="logo mb-3 mr-3" alt="bookstore logo" src="../assets/tetris-T-block-plain.png">
  </div>
</template>

<script>
export default {
  name: "Footer",
  props: {}
};
</script>

<style scoped>
.footer_container {
  height: 300px;
  width: 100%;
}

.text_mirror {
  transform: scale(-1, 1);
}

.footer_text_special_mirror {
  transform: scale(-1, -1);
}

.title_text {
  font-family: monospace !important;
  text-align: center;
}
</style>
