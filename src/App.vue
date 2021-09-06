<template>
  <div>
    <ul>
      <li v-for="(item, idx) in items" :key="idx">
        {{ item }}
      </li>
    </ul>
    <button @click="addAndUpdate">Add and update</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { name: "Alpha", price: 1 },
        { name: "Beta", price: 2 },
      ],
    };
  },
  methods: {
    addAndUpdate() {
      console.log(this.items);
      const newItem = { name: "New", price: "-" };
      this.items.push(newItem);

      console.log("here", this.items[this.items.length - 1] === newItem);
      setTimeout(() => {
        /////newItem.price = "over 9000";
        this.items[this.items.length - 1].price = 345;
      }, 3000);
    },
  },
};
</script>
