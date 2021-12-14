<template>
  <div>
    <h1>Todos</h1>
    <todo-list title="Todo List"></todo-list>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';
export default {
  name: 'Todos.vue',
  components: {
    TodoList
  }
};
</script>

<style scoped>

</style>
