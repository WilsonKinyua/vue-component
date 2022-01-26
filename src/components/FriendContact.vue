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
  </li>
</template>

<script>
export default {
  //   props: [
  //       'name',
  //       'phone',
  //       'age',
  //       'emailAddress'
  //   ],
  props: {
    name: String,
    phone: String,
    emailAddress: String,
    age: String
  },
  data() {
    return {
      detailsAreVisible: false,
      //   friend: {
      //     id: "manuel",
      //     name: "john manuel",
      //     age: 23,
      //     phone: "334 434 3434",
      //     email: "john@mail.com",
      //   },
    };
  },

  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
  },
};
</script>