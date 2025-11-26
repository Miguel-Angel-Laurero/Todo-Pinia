<script setup>
import {ref} from 'vue'

const todo = ref('')

const store = useTodoListStore()

function addItemAndClear(item){
    if(item.length === 0){
        return
    }
    store.addTodo(item)
    todo.value = ''
}

</script>

<template>
    <div>
        <form @submit.prevent="addItemAndClear(todo)">
            <input v-model="todo" type="text" /><button>Add</button>
        </form>
    </div>
</template>

<style>
#app{
    font-family: Avenir,Arial, Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color:#2c3e50;
}
</style>