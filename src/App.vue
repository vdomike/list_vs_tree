<template>
  <div id="app">
    <list-component
      :items="items"
      @onDelete="toggleSelected"
    />
    <tree-component
      :items="items"
      @onChange="toggleSelected"
    />
  </div>
</template>

<script>
import ListComponent from "../src/components/ListComponent";
import TreeComponent from "../src/components/TreeComponent";

export default {
  name: "App",
  components: { ListComponent, TreeComponent },
  data() {
    return {
      items: {
        name: "root",
        selected: false,
        children: [
          {
            name: "item1",
            selected: true,
            children: [
              {
                name: "item11",
                selected: true,
                children: []
              },
              {
                name: "item12",
                selected: false,
                children: []
              }
            ]
          },
          {
            name: "item2",
            selected: false,
            children: [
              {
                name: "item21",
                selected: true,
                children: []
              },
              {
                name: "item22",
                selected: false,
                children: []
              }
            ]
          }
        ]
      }
    };
  },
  methods: {
    toggleSelected(item) {
      item.selected = !item.selected;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
}
</style>
