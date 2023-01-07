<template>
  <div>
    <ul>
      <li v-for="list in lists" :key="list.id">
        <my-item :list="list" @remove="$emit('remove', list)" />
      </li>
    </ul>
  </div>
</template>

<script>
import MyItem from "./MyItem.vue";
export default {
  components: { MyItem },
  name: "my-list",
  props: {
    lists: {
      type: Array,
      required: true,
    },
  },
  emits: ["remove"],
};
</script>

<style scoped>
ul {
  font-family: "Comfortaa", cursive;
  font-weight: 500;
  list-style-type: none;
  padding: 0;
}
</style>
