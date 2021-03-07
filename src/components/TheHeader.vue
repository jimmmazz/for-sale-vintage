<template>
  <div class="container">
    <header>
      <h1 class="logo">
        <span class="r">R</span>ed's <span class="r">R</span>enewable's
      </h1>
      <ul class="list">
        <li class="list-item">
          <button v-on:click="catName(home)" class="btn">
            Home
          </button>
        </li>
        <li class="list-item">
          <button v-on:click="catName(sets)" class="btn">
            Set's
          </button>
        </li>
        <li class="list-item">
          <button v-on:click="catName(chairs)" class="btn">
            Chair's
          </button>
        </li>
        <li class="list-item">
          <button v-on:click="catName(tables)" class="btn">
            Table's
          </button>
        </li>
        <li class="list-item">
          <button v-on:click="login" class="btn">
            Login
          </button>
        </li>
      </ul>
    </header>
  </div>
</template>

<script>
export default {
  emits: ['catName', 'log-in'],
  data() {
    return {
      sets: "Set's",
      chairs: "Chair's",
      tables: "Table's",
      home: 'home',
      isLoggedIn: false,
    };
  },
  methods: {
    catName(cat) {
      // console.log(cat);
      this.$emit('catName', cat);
    },
    login() {
      // console.log(value)
      this.$emit('log-in', { isLoggedIn: true });
    },
  },
};
</script>

<style scope>
header,
.list {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5em 1em 0.5em;
}

header {
  box-shadow: 2px 2px 40px rgba(221, 221, 221, 0.2);
}

.logo,
.list-item {
  padding: 0 1rem;
  font-family: 'Roboto', sans-serif;
  color: #333;
}

.logo {
  text-transform: uppercase;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.1;
}

.list-item {
  font-size: 0.75rem;
  font-weight: 300;
  padding: 0;
}

.r {
  font-size: 2rem;
  color: rgb(190, 54, 20);
  font-family: 'Cinzel', serif;
  font-weight: 600;
}
</style>
