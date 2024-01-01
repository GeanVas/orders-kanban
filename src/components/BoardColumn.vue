<script lang="ts">
import { defineComponent } from 'vue';
import draggable from 'vuedraggable';
import Order from './Order.vue'

export default defineComponent({
  components: {
    draggable,
    Order,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    orders: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      drag: false,
    };
  },
});
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
            <Order :item="element" />
          </template>
        </draggable>
      </div>
</template>