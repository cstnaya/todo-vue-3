<template>
    <div class="todo-item">
        <label>
            <input type="checkbox" v-model="todo.done" />
            <span>{{ todo.name }}</span>
        </label>
        <button @click="emit('removeTodo', todo.name)">x</button>
    </div>
</template>

<script setup>
const props = defineProps({
    todo: {
        required: true,
        default: {},
        type: Object
    },
})

const emit = defineEmits(['removeTodo']);
</script>

<style scoped>

label span {
    padding: 0 1.5rem;
}

input[type="checkbox"]:checked~span {
    text-decoration: line-through;
}

button {
    font-size: 0.7rem;
    padding: 3px 7px;
    border-radius: 50%;
}
</style>