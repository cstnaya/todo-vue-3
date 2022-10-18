<script>
import { ref } from "vue";

export const useHideCompletedComponent = () => {
    const hideCompleted = ref(false);

    const changeCompleted = () => {
        hideCompleted.value = !hideCompleted.value
    };

    return {
        hideCompleted,
        changeCompleted,
    };
};
</script>