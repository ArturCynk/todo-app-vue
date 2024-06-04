<template>
    <div class="todo-item">
        <span>{{todo.text}}</span>
        <butoon @click="$emit('delete-todo',todo.id)">Delete</butoon>
    </div>
</template>

<script>
export default {
    name: 'TodoItem',
    props: {
        todo: Object
    }
}
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  margin: 10px 0;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  background: red;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}

button:hover {
  background: darkred;
}
</style>