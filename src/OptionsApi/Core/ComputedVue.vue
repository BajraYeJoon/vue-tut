<template>
  <h2>{{ firstName }} {{ lastName }}</h2>
  <h2>Computed {{ firstName }} {{ lastName }}</h2>

  <!-- computed setter to change the value -->
  <button @click="changeName">Change Name</button>

  <h4>
    Total - {{ items.reduce((total, curr) => (total = total + curr.price), 0) }}
  </h4>
  <h4>Computed Total - {{ totalPrice }}</h4>

  <button @click="items.push({ id: 4, price: 600 })">Add item</button>

  <!-- computed properties and v-for -->
  <h2 v-for="item in expensive" :key="item.id">{{ item.price }}</h2>
</template>

<script>
export default {
  data() {
    return {
      firstName: "john",
      lastName: "doe",

      items: [
        {
          id: 1,
          price: 100,
        },
        {
          id: 2,
          price: 400,
        },
        {
          id: 3,
          price: 150,
        },
      ],
    };
  },

  methods: {
    changeName() {
      this.fullName = "Mary Jane";
    },
  },

  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const names = value.split(" ");
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },

    totalPrice() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },

    expensive() {
      return this.items.filter((item) => item.price > 100);
    },
  },
};
</script>

<style></style>
