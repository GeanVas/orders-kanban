<script lang="ts">
import draggable from "vuedraggable";

import Order from "./components/Order.vue";
import BoardColumn from "./components/BoardColumn.vue";

export default {
  name: "App",
  components: {
    draggable,
    Order,
    BoardColumn,
  },
  data() {
    return {
      drag: false,
      orders: [
        {
          id: 1,
          client: "Adrian Schubert",
          date: "2023-12-20",
          recipes: [],
        },
        {
          id: 2,
          client: "Violet Gates",
          date: "2023-12-20",
          recipes: [],
        },
        {
          id: 3,
          client: "Steve Jobs",
          date: "2023-12-20",
          recipes: [],
        },
      ],
    };
  },
};
</script>

<template>
  <main>
    <h1 class="text-3xl font-bold text-center">Orders</h1>
    <div class="grid-container">
      <BoardColumn title="To do" :orders="orders" :group="orders"/>
      <BoardColumn title="In progress" :orders="orders" :group="orders" />
      <BoardColumn title="Done" :orders="orders" />
    </div>
  </main>
</template>

<style lang="scss">
.grid-container {
  display: grid;
  grid-auto-flow: column;
  grid-auto-columns: 1fr;
}
.moving-card {
  @apply opacity-50 bg-gray-100 border border-blue-500;
}
</style>
