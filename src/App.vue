<template>
  <div class="app">
    <my-form @create-post="addList" />
    <my-list :lists="lists" @remove="removeItem" />
  </div>
</template>

<script>
import MyForm from "./components/MyForm.vue";
import MyList from "./components/MyList.vue";
export default {
  components: { MyForm, MyList },
  data() {
    return {
      lists: [],
    };
  },
  methods: {
    addList(list) {
      if (list.firstName !== "" && list.lastName !== "" && list.age !== "") {
        this.lists.push(list);
      }
    },
    removeItem(list) {
      this.lists.splice(list.id - 1, 1);
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300&display=swap");

.app {
  font-family: "Comfortaa", cursive;
  margin: 50px auto;
  width: 1200px;
}
</style>
