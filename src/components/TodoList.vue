<template>
  <div>
    <!-- :key="id" 不能重複的值，所以用uuid來生成id值-->
    <div v-for="todo in allTodos" :key="todo.id">
      <TodoItem :todo="todo" />
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem';
import { mapGetters} from "vuex";

export default {
  components: {
    TodoItem
  },
  computed: {
    ...mapGetters(['allTodos'])
  }
};

</script>

<style scoped>
</style>
