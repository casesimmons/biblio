<template>
  <base-card>
    <form>
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="5" />
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" />
      </div>
      <div class="submit-button">
        <base-button type="submit">Add Entry</base-button>
      </div>
    </form>
  </base-card>
</template>

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
  float: right;
}
</style>
