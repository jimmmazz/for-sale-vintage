<template>
  <div class="container">
    <main>
      <h1 class="category-title">{{ catTitle }}</h1>
      <BaseCard v-if="catTitle.length > 0" v-bind:items="itemsToShow" />
    </main>
  </div>
</template>

<script>
import items from '../assets/data.json';
import BaseCard from './BaseCard';

export default {
  components: {
    BaseCard,
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

<style>
.category-title {
  margin: 3rem 2rem 1rem;
  text-transform: uppercase;
  font-weight: 300;
  font-family: 'Roboto', sans-serif;
  color: #333;
}
</style>
