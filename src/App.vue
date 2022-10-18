<template>
  <div>
    <HideCompleted :hideCompleted="hideCompleted" @changeCompleted="changeCompleted" />
    <Form @addTodo="addTodo" />
    <TodoList :list="filteredTodos" @removeTodo="removeTodo" />
  </div>
</template>

<script setup>
import Form from "./components/Form.vue";
import TodoList from "./components/TodoList.vue";
import HideCompleted from "./components/HideCompleted.vue";

import { useTodoComponent } from "./logic/useTodoComponent.vue";
import { useHideCompletedComponent } from './logic/useHideCompletedComponent.vue';

import { computed } from "vue";

const { list, addTodo, removeTodo } = useTodoComponent();
const { hideCompleted, changeCompleted } = useHideCompletedComponent();

const filteredTodos = computed(() => {
  return hideCompleted.value ?
    list.value.filter(item => !item.done) :
    list.value
})

</script>