<template>
  <div class="list">
    <h2>Список</h2>
    <ul class="list__content">
      <item-selected
        :item="items"
        @onDelete="$emit('onDelete', $event)"
      />
    </ul>
  </div>
</template>

<script>
import ItemSelected from "./ItemSelected";

export default {
  components: { ItemSelected },
  props: {
    items: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    selectedItems() {
      return this.items.children.filter(item => item.selected);
    }
  }
};
</script>

<style scoped>
.list {
  flex-basis: 50%;
}
.list__content {
  padding: 0;
}
</style>