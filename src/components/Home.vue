<template>
  <div class="container">
    <h1 class="heading">Welcome to our warehouse !</h1>
    <div class="flex-container">
      <img src="/photos/red.jpg" alt="red" />
      <p class="intro">
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s, when an unknown printer took a galley of type and
        scrambled it to make a type specimen book. It has survived not only five
        centuries, but also the leap into electronic typesetting, remaining
        essentially unchanged. It was popularised in the 1960s with the release
        of Letraset sheets containing Lorem Ipsum passages, and more recently
        with desktop publishing software like Aldus PageMaker including versions
        of Lorem Ipsum.
      </p>
    </div>
    <footer class="footer">
      <p class="name"> Reach <span>R</span>ed at</p>
      <p class="phone">813-334-6857</p>
    </footer>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {};
  },
};
</script>

<style scoped>
.heading {
  font-family: 'Roboto', 'sans-serif';
  font-weight: 300;
  color: #333;
  margin: 3rem 2rem 1rem;
}

.flex-container {
  margin: 0 2rem;
  max-width: 100%;
  display: flex;
  justify-content: space-between;
}

img {
  margin-left: 0;
  margin-right: 1rem;
  margin-top: 0;
  margin-bottom: 0;
  width: 300px;
  height: 300px;
  object-fit: contain;
}

.footer {
  font-family: 'Roboto', 'sans-serf';
  font-size: 0.9em;
  margin-left: 2rem;
  margin-top: 1rem;
  display: flex;
  justify-content: center;
}
.name {
  margin-right: 0.5em;
}

span {
  font-family: 'Cinzel', serif;
  font-size: 1.1em;
  color: rgb(190, 54, 20);
  font-weight: 600;
}

@media (max-width: 550px) {
  .heading {
    text-align: center;
  }

  .flex-container {
    flex-direction: column;
    align-items: center;
  }

  img {
    margin-bottom: 1rem;
  }
}
</style>
