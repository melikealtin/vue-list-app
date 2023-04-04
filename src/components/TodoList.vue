<template>
  <div class="itemname">
    <ul>
      <TodoListItem
        v-for="todoItem in provideData.todoList"
        :key="todoItem.id"
        :item="todoItem"
      ></TodoListItem>
    </ul>
  </div>
</template>

<script>
import TodoListItem from "./TodoListItem.vue";

export default {
  components: {
    TodoListItem,
  },
  inject: ["provideData"],
};
</script>
