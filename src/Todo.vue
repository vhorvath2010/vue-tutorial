<script>
// Each todo will have a unique id
let id = 0

export default {
    data() {
        return {
            newTodo: '',
            todos: []
        }
    },
    methods: {
        addTodo() {
            this.todos.push({ id: id++, text: this.newTodo })
            this.newTodo = '';
        },
        removeTodo(todoToRemove) {
            this.todos = this.todos.filter(todo => {
                return todoToRemove !== todo;
            })
        }
    }
}

</script>

<template>
    <h1>Todo List</h1>
    <input v-model="newTodo">
    <button @click="addTodo">Add to List</button>
    <ul>
        <li v-for="todo in todos" :key="todo.id">
            {{ todo.text }}
            <button @click="removeTodo(todo)">X</button>
        </li>
    </ul>
</template>