<script lang="ts">
import draggable from "vuedraggable";

import order from "./components/Order.vue";

export default {
  name: "App",
  components: {
    draggable,
    order,
  },
  data() {
    return {
      drag: false,
      orders: [
        {
          id: 1,
          client: "Adrian Schubert",
          date: "2023-12-20",
          recipes: []
        },
        {
          id: 2,
          client: "Violet Gates",
          date: "2023-12-20",
          recipes: []
        },
        {
          id: 3,
          client: "Steve Jobs",
          date: "2023-12-20",
          recipes: []
        },
      ],
    };
  },
};
</script>

<template>
  <div class="flex m-10">
    <draggable
      tag="ul"
      class="w-full max-w-md"
      ghost-class="moving-card"
      v-model="orders"
      group="people"
      @start="drag = true"
      @end="drag = false"
      item-key="id"
      :animation="200"
    >
      <template #item="{ element }">
        <order :item="element" />
      </template>
    </draggable>
  </div>
</template>

<style lang="scss">
.moving-card {
  @apply opacity-50 bg-gray-100 border border-blue-500;
}
</style>
