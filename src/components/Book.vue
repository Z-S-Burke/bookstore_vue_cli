<template>
  <div>
    <div class="flip-card m-1">
      <div class="flip-card-inner d-flex">
        <div class="flip-card-front bg-dark">
          <img class="flip-card" v-bind:src="oneBook.portada">
        </div>
        <div class="flip-card-back" id="info">
          <h3 class="mb-2 mt-3">{{oneBook.titulo}}</h3>
          <p class="mx-3 mt-3">{{oneBook.descripcion}}</p>
          <div>
            <b-button @click="toggleModal"> Get Fancy </b-button>
          </div>
        </div>
      </div>
    </div>
    <b-modal v-model="showModal" :title="oneBook.titulo">
      <img :src="oneBook.detalle">
    </b-modal>
  </div>
</template>

<script>
export default {
  name: "Book",
  props: ["oneBook"],
  data() {
    return {
      showModal: false
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    }
  }
};
</script>

<style scoped>
/* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  width: 280px;
  height: 350px;
  border: 1px solid #f1f1f1;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  color: black;
}

/* Style the back side */
.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
}

.logo {
  height: 250px;
  width: 250px;
}
img {
  width: 100%;
}
</style>
