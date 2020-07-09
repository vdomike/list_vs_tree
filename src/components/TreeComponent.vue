<template>
  <div class="tree">
    <h2>Дерево</h2>
    <div class="tree__content">
      <item-checkbox
        :item="items"
        :tab="0"
        @change="$emit('onChange', $event)"
      />
    </div>
  </div>
</template>

<script>
import ItemCheckbox from "./ItemCheckbox";

export default {
  components: { ItemCheckbox },
  props: {
    items: {
      type: Object,
      default: () => {}
    }
  }
};
</script>

<style scoped>
.tree {
  flex-basis: 50%;
}
.tree__content {
  display: flex;
  justify-content: center;
}
</style>