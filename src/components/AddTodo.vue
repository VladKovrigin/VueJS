<template>
  <div>
    <div class="d-flex flex-row mb-4">
      <input v-model="inputValue" class="form-control mr-2" placeholder="Новая задача">
      <button @click="addTodo(inputValue, $event)" class="btn btn-primary">
        Добавить
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      inputValue: '',
      disableButton: false,
    }
  },
  methods: {
    addTodo() {
      this.$emit('add-todo', { todo: this.inputValue });
      this.inputValue = '';
    },
  }
}
</script>

<style scoped>

</style>