<template>
    <div>
        <router-link to="/">Home</router-link>
            <AddTodo
                @add-todo="addTodo"
            />
        <hr>
        <todolist
                v-if="todos.length"
                v-bind:todos="todos"
                @remove-todo="remove-todo"
        />
        <p v-else>No todos</p>
    </div>
</template>

<script>
    import todolist from "../components/todolist";
    import AddTodo from "../components/AddTodo"
    export default {
        name: 'App',
        data(){
            return{
                todos:[
                    {id:1, title:'Buy', completed:false},
                    {id:2, title:'sale', completed:false},
                    {id:3, title:'drop', completed:false},
                ]
            }
        },
        mounted() {
                // fetch('https://jsonplaceholder.typicode.com/todos')
                //     .then(response => response.json())
                //     .then(json=>{
                //         this.todos = json;
                //     })
        },
        methods:{
            removeTodo(id){
                this.todos = this.todos.filter(t => t.id !== id)
            },
            addTodo(todo){
                this.todos.push(todo)
            }
        },
        components: {
            AddTodo, todolist
        }
    }
</script>
