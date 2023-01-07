<template>
  <form @submit.prevent>
    <my-inputs
      v-model:firstName="list.firstName"
      v-model:lastName="list.lastName"
      v-model:age.number="list.age"
    />
    <my-buttons @click="addPost">Добавить</my-buttons>
  </form>
</template>

<script>
import MyButtons from "./MyButtons.vue";
import MyInputs from "./MyInputs.vue";
let id = 1;
export default {
  components: { MyInputs, MyButtons },
  name: "my-form",
  data() {
    return {
      list: {
        id: id++,
        firstName: "",
        lastName: "",
        age: "",
      },
    };
  },
  emits: ["create-post"],
  methods: {
    addPost() {
      this.$emit("create-post", this.list);
      this.list = {
        id: id++,
        firstName: "",
        lastName: "",
        age: "",
      };
    },
  },
};
</script>

<style>
</style>