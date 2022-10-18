<script>
import { ref } from "vue";

export const useTodoComponent = () => {
    const list = ref([]);

    let id = 0;

    const addTodo = (todo) => {
        list.value.push({
            id: id++,
            name: todo,
            done: false,
        })
    };

    const removeTodo = (todo) => {
        list.value = list.value.filter(it => it.name !== todo);
    };

    return {
        list, addTodo, removeTodo
    };
};
</script>