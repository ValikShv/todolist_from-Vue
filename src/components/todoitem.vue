<template>
    <li>
        <span v-bind:class="{done: todo.complement}" >
        <input type="checkbox" v-on:change="todo.complited =!todo.complited">
        <strong>{{index+1 }}</strong>
            {{todo.title}}
        </span>
        <button class="rm" v-on:click="$emit('remove-todo', todo.id)">&times</button>
    </li>


</template>

<script>
export default {
    props:{
        todo:{
            type: Object,
            required: true,
        },
        index: Number,
    }
}
</script>

<style scoped>
    li{
        border: 1px solid #ccc;
        display: flex;
        justify-content: space-around;
        padding: 2rem;
        margin-bottom: 1rem;
    }
    .rm{
        background: red;
        color: #fff;
        border-radius: 50%;
        font-weight: bold;
    }
    input{
        margin-right: 1rem;
    }
    .done{
        text-decoration: none;
    }
</style>
