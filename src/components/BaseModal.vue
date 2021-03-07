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
  font-size: 1.1rem;
  color: rgb(255, 228, 221);
  padding: 5px 15px;
}

.modal-heading {
  z-index: 10;
  color: #333;
  font-size: 1.75rem;
  font-family: 'Roboto', sans-serif;
  font-weight: 300;
}

.modal-header {
  margin: 0 10% 1rem;
  display: flex;
  justify-content: space-between;
}

.descLong {
  color: #666;
  line-height: 1.5;
  margin: 1rem 10%;
}

.images {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.imgLarge {
  margin: auto;
  width: 80%;
  height: 500px;
  object-fit: cover;
  box-shadow: 3px 3px 20px rgba(0, 0, 0, 0.15);
}

.thumbs {
  margin: 1rem;
  width: 100px;
  height: 100px;
}

@media (max-width: 420px) {
  .btn {
    font-size: 1.25rem;
    color: #fff ;
  }

  .modal {
    background-color: #999;
  }
  .modal-header {
    margin: 1em 5% 1rem;
  }

  .modal-heading {
    font-size: 1.25rem;
  }

  .descLong {
    color: #fff;
  }

  .imgLarge,
  .thumbs {
    width: 90%;
    height: 400px;
  }

  .thumbs {
    margin: auto;
    object-fit: cover;
    box-shadow: 3px 3px 20px rgba(0, 0, 0, 0.15);
  }
}
</style>
