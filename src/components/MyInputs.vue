<template>
  <div>
    <input
      type="text"
      @input="$emit('update:firstName', $event.target.value)"
      :value="firstName"
      placeholder="Имя"
      class="input"
    />
    <input
      type="text"
      @input="$emit('update:lastName', $event.target.value)"
      :value="lastName"
      placeholder="Фамилия"
      class="input"
    />
    <input
      type="text"
      @input="$emit('update:age', $event.target.value)"
      :value="age"
      placeholder="Возраст"
      class="input"
    />
  </div>
</template>

<script>
export default {
  props: ["firstName", "lastName", "age"],
  emits: ["update:firstName", "update:lastName", "update:age"],
};
</script>

<style scoped>
.input {
  font-family: "Comfortaa", cursive;
  padding: 5px 10px;
  margin-right: 10px;
}
</style>