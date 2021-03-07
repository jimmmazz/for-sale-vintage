<template>
  <TheHeader @cat-name="category" @log-in="loggedIn" />
  <TheMain :catTitle="catTitle" />
  <ItemForm v-if="isLoggedIn" />
</template>

<script>
import TheHeader from './components/TheHeader';
import TheMain from './components/TheMain';
import ItemForm from './components/ItemForm';

export default {
  name: 'App',
  // provide: {
  //   showItem: false,
  // },
  data() {
    return {
      catTitle: 'home',
      isLoggedIn: false,
    };
  },
  components: {
    TheHeader,
    TheMain,
    ItemForm,
  },
  methods: {
    category(value) {
      this.catTitle = value;
    },
    loggedIn(value) {
      console.log(value);
      this.isLoggedIn = value.isLoggedIn;
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600&family=Roboto:wght@300;400&display=swap');

body {
  background: linear-gradient(45deg, transparent, rgba(0, 0, 0, 0.5));
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.btn {
  padding: 3px 12px;
  border-radius: 2px;
  border: none;
  background-color: transparent;
  color: #ddd;
  transition: 300ms ease;
}

.btn:hover {
  background-color: rgba(221, 221, 221, 0.2);
  color: #333;
}
</style>
