<script>
// Each todo will have a unique id
let id = 0

export default {
    data() {
        return {
            newTodo: '',
            todos: [],
            hideCompleted: false,
        }
    },
    computed: {
        filteredTodos() {
            if (this.hideCompleted) {
                return this.todos.filter(todo => {
                    return !todo.completed;
                })
            } else {
                return this.todos;
            }
        }
    },
    methods: {
        addTodo() {
            this.todos.push({ id: id++, text: this.newTodo, completed: false })
            this.newTodo = '';
        },
        removeTodo(todoToRemove) {
            this.todos = this.todos.filter(todo => { return todoToRemove !== todo; })
        },
        toggleHideCompleted() {
            this.hideCompleted = !this.hideCompleted;
        }
    }
}

</script>

<template>
    <h1>Todo List</h1>
    <form @submit.prevent="addTodo">
        <input v-model="newTodo">
        <button>Add to List</button>
    </form>
    <ul>
        <li v-for="todo in filteredTodos" :key="todo.id">
            <input type="checkbox" v-model="todo.completed">
            <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
            <button @click="removeTodo(todo)">X</button>
        </li>
    </ul>
    <button @click="toggleHideCompleted">
        {{ hideCompleted ? "Show all" : "Hide Completed" }}
    </button>
</template>

<style scoped>
.completed {
    text-decoration: line-through;
}
</style>