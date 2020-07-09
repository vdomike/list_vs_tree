<template>
  <div class="selected">
    <div
      class="selected__item"
      v-if="item.selected"
    >
      <div class="selected__item-name">{{ item.name }}</div>
      <div
        class="selected__delete"
        @click="$emit('onDelete', item)"
      >X</div>
    </div>
    <item-selected
      v-for="(item, index) in item.children"
      :item="item"
      @onDelete="$emit('onDelete', $event)"
      :key="`selected-${item.name}-${index}`"
    />
  </div>
</template>

<script>
export default {
  name: "ItemSelected",
  props: {
    item: {
      type: Object
    }
  }
};
</script>

<style scoped>
.selected__item {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 10px;
}
.selected__item-name {
  padding: 10px;
  background: rebeccapurple;
  color: #ffffff;
  width: 100px;
  border-radius: 5px;
}
.selected__delete {
  width: 25px;
  height: 25px;
  background: teal;
  color: #ffffff;
  border-radius: 5px;
  margin-left: 15px;
  line-height: 25px;
  cursor: pointer;
}
</style>