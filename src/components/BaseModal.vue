<template>
  <div class="modal-container">
    <div class="modal">
      <div class="modal-header">
        <h1 class="modal-heading">{{ itemToShow[0].lable }}</h1>
        <button v-on:click="closeModal" class="btn">Close</button>
      </div>
      <div class="gallery">
        <img :src="picToShow" alt="" class="imgLarge" />
        <div class="descLong">{{ itemToShow[0].description }}</div>
      </div>
      <div class="images">
        <img
          v-for="item in itemToShow[0].imageSet"
          :key="item.index"
          :src="item"
          :alt="item"
          v-on:click="switchPic"
          class="thumbs"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  emits: ['close-modal'],
  props: ['itemToShow'],
  data() {
    return {
      picToShow: this.itemToShow[0].imageThumbNail,
    };
  },
  methods: {
    closeModal() {
      this.$emit('close-modal');
    },
    switchPic(value) {
      console.log(value.target.attributes[0].value);
      this.picToShow = value.target.attributes[0].value;
    },
  },
};
</script>

<style scoped>
.btn {
  color: white;
}
.modal-container {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.8);
  height: 100vh;
  width: 100vw;
}

.modal-heading {
  z-index: 10;
  color: #ccc;
  /* margin: 1rem 10%; */
  font-family: 'Roboto', sans-serif;
  font-weight: 300;
}

.modal-header {
  margin: 0 10% 1rem;
  display: flex;
  justify-content: space-between;
}

.modal {
  position: absolute;
  width: 90%;
  padding: 1rem;
  left: 50px;
  right: 50px;
  top: 50px;
  bottom: 50px;
  background-color: rgba(200, 200, 200, 0.5);
}

.descLong {
  color: #ccc;
  line-height: 1.5;
  margin: 1rem 10%;
}

.images {
  display: flex;
  justify-content: center;
}

.imgLarge {
  margin: auto;
  width: 80%;
  height: 500px;
  object-fit: cover;
}

.thumbs {
  margin: 1rem;
  width: 100px;
  height: 100px;
}
</style>
