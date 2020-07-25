<template>
  <div id="todo-item" v-bind:class="{ active: todo.status }">
    <div>
      <span class="number">{{ index + 1 }}</span>
      <input type="checkbox" v-model="todo.status" />
    </div>
    <span>{{ todo.text }}</span>
    <span
     class='delete'
     v-on:click="$emit('on-delete-item-todo', todo.id)"
     >&times;</span>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      id: Number,
      text: String,
      status: Boolean,
    },
    index: Number,
  },
};
</script>

<style scoped>
#todo-item {
  height: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 5px 15px;
  border: 1px solid #ccc;
  box-shadow: 2px 2px 5px 0px rgba(0, 0, 0, 0.3);
  border-radius: 4px;
  margin-bottom: 10px;
  cursor: pointer;
  background: #fff;
}

.active {
  text-decoration: line-through;
}

.number {
  font-weight: 700;
}

.delete {
  /* padding: 5px; */
  background: red;
  border-radius: 50%;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5em;
}
</style>
