<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-buttons",
};
</script>

<style scoped>
.btn {
  margin: 10px 0;
  padding: 10px;
  cursor: pointer;
  border: 1px solid #fff;
}

.btn:hover {
  background: rgb(194, 194, 194);
}
</style>