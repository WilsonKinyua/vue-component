<template>
  <section>
    <h2>My friends</h2>
    <new-friend @add-contact="addContact"></new-friend>
    <friend-contact
      @delete="deleteContact"
      v-for="friend in friends"
      :key="friend.id"
      :name="friend.name"
      :age="friend.age"
      :phone="friend.phone"
      :email-address="friend.email"
      :is-favourite="friend.isFavourite"
    ></friend-contact>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          name: "john",
          id: "johnie",
          age: "23",
          phone: "1234567",
          isFavourite: true,
        },
        {
          name: "mary",
          id: "maryie",
          age: "23",
          phone: "1234567",
        },
      ],
    };
  },
  methods: {
    addContact(name, phone, email) {
      const newFriend = {
        name: name,
        phone: phone,
        email: email,
        id: new Date().toISOString(),
        age: "23",
        isFavourite: false,
      };
      this.friends.push(newFriend);
    },
    deleteContact(friendId) {
      this.friends = this.friends.filter((friend) => friend.id !== friendId);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Jost&display=swap");

* {
  box-sizing: border-box;
}

html {
  font-family: "Jost", sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #58004d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li,
#app form {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}

#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#app button:hover,
#app button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
#app input {
  font: inherit;
  padding: 0.15rem;
}
#app label {
  font-weight: bold;
  margin-right: 1rem;
  width: 7rem;
  display: inline-block;
}
#app form div {
  margin: 1rem 0;
}
</style>