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
      users: [
        {
          id: 1,
          name: "Adrian Schubert",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png",
        },
        {
          id: 2,
          name: "Violet Gates",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png",
        },
        {
          id: 3,
          name: "Steve Jobs",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png",
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
      v-model="users"
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
