<template>
  <BaseModal
    v-if="itemToShow.length"
    :itemToShow="itemToShow"
    @close-modal="closeModal"
  />
  <div v-else class="card-container">
    <div
      v-for="item in items"
      :key="item.id"
      v-on:click="getAllPics(item.id)"
      class="card"
    >
      <h3 class="card-lable">{{ item.label }}</h3>
      <img :src="item.imageThumbNail" :alt="item.label" />
      <p class="card-description">
        {{ item.descriptionShort }}
      </p>
      <p class="price">Price: ${{ item.price }}</p>
    </div>
  </div>
</template>

<script>
import BaseModal from './BaseModal';

export default {
  // inject: ['showItem'],
  components: {
    BaseModal,
  },
  props: ['items'],
  data() {
    return {
      // displayItem: this.showItem,
      itemToShow: [],
    };
  },
  methods: {
    getAllPics(id) {
      this.itemToShow = this.items.filter(item => item.id === id);
      console.log(this.itemToShow);
      // console.log(this.showItem);
      // this.showItem = true;
      // console.log(this.showItem);
    },
    closeModal() {
      this.itemToShow = [];
      // this.showItem = false;
    },
  },
};
</script>

<style scoped>
.card-container {
  width: 100%;
  padding: 1rem;
  display: flex;
  flex-direction: row;
  justify-content: left;
  flex-wrap: wrap;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: left;
  background-color: hsl(0, 0%, 98%);
  border-radius: 5px;
  outline: 1px solid rgb(255, 255, 255);
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.12);
  max-width: 220px;
  padding: 0.5em;
  margin: 1em;
  transition: all 200ms ease;
}

.card:hover {
  cursor: pointer;
  background-color: hsl(0, 0%, 94%);
  outline: 1px solid rgb(182, 182, 182);
}

.card-lable {
  color: #000;
  font-weight: 300;
  font-family: 'Roboto', sans-serif;
}

img {
  margin: 0.5em 0;
  border-radius: 3px;
  border: 1px solid #777;
}

.card-description {
  color: #777;
  font-size: 0.8em;
  line-height: 1.6;
}

.price {
  font-size: 0.8rem;
}

@media (max-width: 550px) {
  .card-container {
    align-items: center;
    justify-content: center;
  }

  .card {
    max-width: 300px;
  }
}
</style>
