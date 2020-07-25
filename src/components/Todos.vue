<template>
  <div>
    <div class="todos" v-if="todos.length > 0">
      <div  v-for="(todo, i) in todos" :key="todo.id">
        <Todo
         v-bind:todo="todo"
          v-bind:index="i"
          v-on:on-delete-item-todo="deleteItem"
           />
      </div>
    </div>
    <div v-else>
      Пока нет зписей
    </div>
  </div>
</template>

<script>
import Todo from "./Todo";
export default {
  components: {
    Todo,
  },
  props: {
    todos: Array,
  },
  methods: {
    deleteItem(id) {
      this.$emit('delete-item', id)
    }
  }
};
</script>

<style>
  .todos {
    padding-top: 10px;
  }
</style>
