<template>
  <div class="node">
    <label
      class="node__label"
      :style="{ marginLeft: `${tab*30}px`}"
    >
      <input
        type="checkbox"
        :checked="checked"
        @change="$emit('change', item)"
      />
      {{item.name}}
    </label>
    <item-checkbox
      v-for="(item, index) in item.children"
      :item="item"
      :checked="item.selected"
      :tab="tab+1"
      @change="$emit('change', $event)"
      :key="`checkbox-${item.name}-${index}`"
    />
  </div>
</template>

<script>
export default {
  name: "ItemCheckbox",
  model: {
    prop: "checked",
    event: "change"
  },
  props: {
    item: {
      type: Object
    },
    tab: {
      type: Number
    },
    checked: {
      type: Boolean
    }
  }
};
</script>

<style scoped>
.node__label {
  padding: 10px;
  background: teal;
  color: #ffffff;
  width: 100px;
  display: block;
  border-radius: 5px;
  margin-bottom: 10px;
}
</style>