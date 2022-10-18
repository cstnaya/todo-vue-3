<template>
    <button @click="emit('changeCompleted')">
        {{ hideCompleted ? "Show All" : "Hide Completed" }}
    </button>
</template>

<script setup>
const emit = defineEmits(['changeCompleted']);

const props = defineProps({
    hideCompleted: {
        default: false,
        type: Boolean
    }
});
</script>