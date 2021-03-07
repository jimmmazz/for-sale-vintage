<template>
  <div class="container">
    <main>
      <div v-if="catTitle !== 'home'">
        <h1 class="category-title">{{ catTitle }}</h1>
        <BaseCard v-bind:items="itemsToShow" />
      </div>
      <div v-else>
        <Home />
      </div>
    </main>
  </div>
</template>

<script>
import items from '../assets/data.json';
import BaseCard from './BaseCard';
import Home from './Home';

export default {
  components: {
    BaseCard,
    Home,
  },
  props: ['catTitle'],
  data() {
    return {
      items,
    };
  },
  computed: {
    itemsToShow() {
      return items.filter(
        item => item.category === this.catTitle.trim().toLowerCase(),
      );
    },
  },
};
</script>

<style scoped>
.category-title {
  margin: 3rem 2rem 1rem;
  text-transform: uppercase;
  font-weight: 300;
  font-family: 'Roboto', sans-serif;
  color: #333;
}

@media (max-width: 550px) {
  div {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .category-title {
    margin: 1rem 2rem 1rem;
    text-align: center;
  }
}
</style>
