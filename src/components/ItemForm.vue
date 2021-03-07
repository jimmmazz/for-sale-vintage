<template>
  <div class="container">
    <form class="form">
      <label for="category" class="form-label">Category</label>
      <input type="text" class="form-control" name="category" id="category" />
      <label for="lable" class="form-label">Lable</label>
      <input type="text" class="form-control" name="lable" id="lable" />
      <label for="desc-short" class="form-label">Short Description</label>
      <textarea
        class="form-control"
        name="desc-short"
        id="desc-short"
        cols="30"
        rows="2"
      ></textarea>
      <label for="desc-long" class="form-label">Short Description</label>
      <textarea
        class="form-control"
        name="desc-long"
        id="desc-long"
        cols="30"
        rows="5"
      ></textarea>
      <label for="price" class="form-label">Price</label>
      <input type="number" class="form-control" name="price" id="price" />
      <label for="image-thumb-nail" class="form-label">Image Thumb Nail</label>
      <input
        type="text"
        class="form-control"
        name="image-thumb-nail"
        id="image-thumb-nail"
      />
      <label for="image-set" class="form-label">Image Set</label>
      <input type="text" class="form-control" name="image-set" id="image-set" />
      <button v-on:click="submitItem" type="button" value="Submit">
        Add Item
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return{}
  },
  methods: {
    submitItem() {
      console.log('submitted');
    },
  },
};
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  max-width: 500px;
  margin: -2rem auto;
}

.form-lable,
.form-control {
  line-height: 1.2;
  font-size: 0.8rem;
  margin: 0.5em 0;
}
</style>
