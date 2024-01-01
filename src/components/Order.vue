<!-- ListItem.vue -->
<template>
  <li
    :key="item.id"
    class="p-4 mb-3 flex justify-between items-center bg-white shadow rounded-lg cursor-move"
  >
    {{ item.client }}
  </li>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";

export default defineComponent({
  props: {
    item: {
      type: Object as PropType<{
        id: number;
        client: string;
        date: string;
        recipes: Array<string>;
      }>,
      required: true,
    },
  },
});
</script>
