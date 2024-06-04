<template>
    <div>
        <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" @delete-todo="deleteTodo" />
        <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a todo" />
    </div>
</template>

<script>
    import TodoItem from './TodoItem.vue';

    export default {
        name: 'TodoList',
        components: {
            TodoItem
        },

        data() {
            return {
                newTodo: '',
                todos: [
                    {id: 1, text: 'Learn Vue.js'},
                    {id: 2, text: 'Build a Todo App'}
                ]
            }
        },
        methods: {
            addTodo(){
                if(this.newTodo.trim()){
                    this.todos.push({id:this.todos.length + 1, text: this.newTodo}),
                    this.newTodo = '';
                }
            },
            deleteTodo(id){
                this.todos = this.todos.filter(todo => todo.id !== id);
            }
        }
    }
</script>

<style scoped>
    input{
        margin-top: 20px;
        padding: 10px;
        font-size: 16px;
    }
</style>
