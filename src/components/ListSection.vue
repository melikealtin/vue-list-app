<template>
  <div class="listsection">
    <div class="todolist">
      <TodoList></TodoList>
    </div>
    <div class="result">
      <ResultBar :itemCount="provideData.todoList.length"></ResultBar>
    </div>
  </div>
</template>

<script>
import TodoList from "./TodoList.vue";
import ResultBar from "./ResultBar.vue";

export default {
  components: {
    TodoList,
    ResultBar,
  },
  inject: ["provideData"],
  props: {
    type: Array,
    required: true,
  },
};
</script>
