<template>
  <div>
    <h2>{{ title }}</h2>
    <div>
      <ul class="todo-list">
        <li
          v-for="todo in todos"
          v-if="todo.completed === false"
          :key="todo.id"
          :class="todo.completed ? 'completed' : ''"
        >
          {{ todo.title }}
          <button @click="toggleTodo(todo.id)">Toggle</button>
        </li>
      </ul>
      <h3>Completed Todos</h3>
      <ul class="completed-todo-list">
        <li
          v-for="todo in completedTodos"
          :key="todo.id"
          :class="todo.completed ? 'completed' : ''"
        >
          {{todo.title}}
          <button @click="toggleTodo(todo.id)">Toggle</button>
        </li>
      </ul>
      <input v-model="newItemText">
      <button @click="addTodo">Add Todo</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: {
    title: {
      required: true,
      type: String
    }
  },
  data () {
    return {
      todos: [],
      newItemText: null
    };
  },
  computed: {
    completedTodos: function () {
      return this.todos.filter(todo => todo.completed === true);
    },
  },
  methods: {
    addTodo: function () {
      console.log('addToDo has been run');
      this.todos.push({
        id: this.todos.length + 1,
        title: this.newItemText,
        completed: false,
      });
      this.newItemText = null;
    },
    toggleTodo: function (idTodo) {
      const found = this.todos.find(todo => todo.id === idTodo);
      found.completed = !found.completed;
    }
  },
  created: function () {
    console.log('I have been created!');
    fetch('https://jsonplaceholder.typicode.com/todos/')
      .then(response => response.json())
      .then(json => this.todos = json);
  }
};
</script>

<style>

.todo-list {
  color: #00720e;
}

.completed-todo-list {
  color: #3b0072;
}

.completed {
  text-decoration: line-through;
}

</style>
