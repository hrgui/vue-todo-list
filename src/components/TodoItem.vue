<template>
  <div>
    <input type="checkbox" v-model="todo.completed">
    <s v-if="todo.completed">
      {{todo.text}}
    </s>
    <span v-if="!todo.completed">
          {{todo.text}}
        </span>
  </div>
</template>

<script>
  export default {
    name: 'todo-item',
    props: ['todo'],
    data() {
      return {};
    },
  };
</script>