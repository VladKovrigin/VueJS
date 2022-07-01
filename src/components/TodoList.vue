<template>
  <div>
    <add-todo
        @add-todo="addTodo"/>
    <div class="d-flex justify-content-center flex-column">
      <div class="d-flex flex-row mb-3">
        <p class="mr-1 m-0 align-self-center">
          Сортировка
        </p>
        <button @click="sort()" class="btn btn-primary mr-2">
          новее
        </button>
        <button @click="asort()" class="btn btn-primary">
          старее
        </button>
      </div>
      <ul class="d-flex flex-column justify-content-center">
        <li v-for="todo in todos" class="d-flex mb-2" v-bind:key="todo">
            <span :class="{completed: todo.completed}" class="align-self-center">
              <input type="checkbox"
                     @change="todo.completed = !todo.completed"
                     class="form-check-input align-self-center">
              {{ todo.task }}
            </span>
          <button @click="deleteTodo(todo.id)" class="btn btn-danger ml-2">
            Удалить
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import AddTodo from "@/components/AddTodo";

export default {
  name: "TodoList",
  components: {
    AddTodo,
  },
  data() {
    return {
      todoId: 2,
      todos: [{
        id: 0,
        task: 'Добавление в список',
        completed: false,
      },
      {
        id: 1,
        task: 'Удаление из списка',
        completed: false,
      },
      {
        id: 2,
        task: 'Сортировка',
        completed: false,
      }],
      newTodo: 'Новая задача'
    }
  },
  methods: {

    addTodo(event) {
      if (event.todo.length) {
        this.todos.push({
          id: ++this.todoId,
          task: event.todo,
          completed: false,
        });
      }
    },
    deleteTodo(id) {
      let index = this.todos.findIndex(item => item.id === id);

      this.todos.splice(index, 1);
    },
    sort() {
      this.todos.sort((a, b) => a['id'] > b['id'] ? 1 : -1);
    },

    asort() {
      this.todos.sort((a, b) => b['id'] > a['id'] ? 1 : -1);
    }
  }
}
</script>

<style scoped>

</style>