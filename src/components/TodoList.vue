<template>
    <ul>
        <li v-for="item in list" :key="item.id">
            <TodoItem :todo="item" @removeTodo="emit('removeTodo')" />
        </li>
    </ul>
</template>

<script setup>
import TodoItem from './TodoItem.vue';

const props = defineProps({
    list: {
        type: Array,
        default: [],
    },
});

const emit = defineEmits(['removeTodo']);

</script>

<style scoped>
ul {
    padding: 0;
}
</style>