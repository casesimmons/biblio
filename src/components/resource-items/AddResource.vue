<template>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          rows="5"
          ref="descInput"
        />
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
      <div class="submit-button">
        <base-button type="submit">Add Entry</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  methods: {
    submitData() {
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDesc = this.$refs.descInput.value;
      const enteredLink = this.$refs.linkInput.value;
      this.addResource(enteredTitle, enteredDesc, enteredLink);
    }
  }
};
</script>

<style scoped>
label {
  color: whitesmoke;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid grey;
  background-color: #black;
  color: whitesmoke;
}

input:focus,
textarea:focus {
  outline: none;
  color: whitesmoke;
  /* border-color: green; */
  background-color: #black;
}

.form-control {
  margin: 1rem 0;
}

.submit-button {
  display: flex;
  justify-content: flex-end;
}
</style>
