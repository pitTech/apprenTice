<template>
    <div>
    <ul>
       <Todoitem v-bind:key="i" v-for="(todo, i) in todos" v-bind:todo="todo" v-bind:index="i" v-on:remove-todo="removeTodo"/>
    </ul>
    </div>

</template>

<script>
import Todoitem from "@/components/Todoitem"
    export default {
        props: ['todos'],
    components: {
        Todoitem
    },
    methods: {
        removeTodo(id) {
            console.log(id)
            this.$emit('remove-todo', id)
        }
    },
    }
</script>

<style lang="scss" scoped>
ul {
        list-style: none;
        margin-top:2.6rem;
        padding: 0;
        margin: 0;
    }
</style>