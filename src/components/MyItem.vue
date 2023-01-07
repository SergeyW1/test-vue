<template>
  <div class="item-list" :key="list.id">
    <span>Имя: {{ list.firstName }}</span>
    <span>Фамилия: {{ list.lastName }}</span>
    <span>Возраст: {{ list.age }}</span>
    <div>
      <my-buttons @click="$emit('remove', list)">Удалить</my-buttons>
    </div>
  </div>
</template>

<script>
import MyButtons from "./MyButtons.vue";
export default {
  components: { MyButtons },
  name: "my-item",
  props: {
    list: {
      type: Object,
      required: true,
    },
  },
  emits: ["remove"],
};
</script>

<style scoped>
.item-list {
  margin: 10px 0;
  display: flex;
  flex-direction: column;
  border: 1px solid;
  padding: 25px;
  border-radius: 5px;
}

.item-list span {
  margin: 10px 0;
}
</style>