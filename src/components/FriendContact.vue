<template>
  <li>
    <header>
      <h1>{{ name }}</h1>
    </header>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <ul v-if="detailsAreVisible">
      <li>Phone: {{ phone }}</li>
      <li>Email: {{ emailAddress }}</li>
      <li>Age: {{ age }}</li>
    </ul>
    <button @click="$emit('delete',id)">Delete</button>
  </li>
</template>

<script>
export default {
  props: {
    name: String,
    phone: String,
    emailAddress: String,
    age: String,
    id: String,
  },
  emits: ["toggle-favorite", "delete"],
  data() {
    return {
      detailsAreVisible: false,
    };
  },

  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>