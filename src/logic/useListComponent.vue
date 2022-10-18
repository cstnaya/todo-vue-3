<script>
import { onMounted, ref } from "vue";

export const useListComponent = () => {
  const list = ref([]);

  onMounted(() => {
    list.value.push(0, 1, 2, 3);
  });

  const addList = (item) => {
    return list.value.push(item);
  };

  return {
    list,
    addList,
  };
};
</script>
