<template>
    <form class="form" @submit.prevent="addTodo">
        <input v-model="input" />
        <button type="submit">Add</button>
    </form>
</template>

<script setup>
import { ref } from 'vue';

const input = ref('');

const emit = defineEmits(['addTodo']);

const addTodo = () => {
    emit('addTodo', input.value);

    input.value = "";
};

</script>

<style scoped lang="scss">
.form {
    padding: 1rem 0;
}

.form input {
    outline: none;
    margin-right: .5rem;
    padding: 5px 7px;
}
</style>