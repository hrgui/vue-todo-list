<template>
  <div>
    <h1>Todo List</h1>
    <ul>
      <li v-for="(todo, i) in todos">
        <todo-item :todo="todo"></todo-item>
        <button @click="removeTodo(todo, i)">Del</button>
      </li>
    </ul>


    <input type="text" v-model="newTodo">
    <button @click="addTodo(newTodo)">Add Todo</button>

  </div>
</template>

<script>
  import TodoItem from './TodoItem';

  export default {
    name: 'todo-list',
    components: { TodoItem },
    data() {
      return {
        newTodo: null,
        todos: [],
      };
    },
    methods: {
      addTodo(v) {
        this.todos.push({ text: v, completed: false });
        this.newTodo = null;
      },
      removeTodo(todo, i) {
        this.todos.splice(i, 1);
      },
    },
  };
</script>

<style scoped>
  li {
    list-style: none;
  }
</style>