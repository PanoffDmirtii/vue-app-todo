<template>
  <div id="dashboard">
    <div class="wrapper">
      <div class="form-block">
        <input class="form-block__input" type="text" v-model="newText" />
        <button @click="addNewTodo">Add</button>
      </div>
      <Todos v-bind:todos="todoList" v-on:delete-item="removeTodo" />
    </div>
  </div>
</template>

<script>
import Todos from "./Todos";
export default {
  components: {
    Todos,
  },
  methods: {
    addNewTodo: function() {
      if (!this.newText) return;
      this.todoList.push({
        id: this.todoList.length + 1,
        text: this.newText,
        status: false,
      });
      this.newText = "";
    },
    removeTodo(id) {
      this.todoList = this.todoList.filter(todo => todo.id !== id)
    },
  },
  data() {
    return {
      todoList: [
        { id: 1, text: "test", status: false },
        { id: 2, text: "test222", status: true },
      ],
      newText: "",
    };
  },
};
</script>

<style scoped>
#dashboard {
  background: rgb(187 220 243 / 67%);
}

.wrapper {
  padding: 20px 30px;
}

.form-block {
  display: flex;
  justify-content: space-between;
  width: 50%;
  margin: 0 auto;
}

.form-block__input {
  padding: 5px;
  border: none;
  border-bottom: 1px solid rgb(7, 11, 17);
  background: transparent;
}

.form-block__input:focus {
  outline: none;
}
</style>
