<!-- ListItem.vue -->
<template>
  <li :key="item.id" class="p-4 mb-3 flex justify-between items-center bg-white shadow rounded-lg cursor-move">
    {{ item.name }}
  </li>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

export default defineComponent({
  props: {
    item: {
      type: Object as PropType<{ id: number; name: string }>,
      required: true,
    },
  },
});
</script>
