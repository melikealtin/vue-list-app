<template>
  <div class="container">
    <div class="content">
      <h3>ToDo App</h3>
      <hr />
      <AddSection :addNewTodo="addNewTodo" @add-todo="addNewTodo"></AddSection>
      <ListSection></ListSection>
    </div>
  </div>
</template>

<script>
import AddSection from "./components/AddSection.vue";
import ListSection from "./components/ListSection.vue";

export default {
  components: {
    AddSection,
    ListSection,
  },
  data() {
    return {
      provideData: {
        todoList: [
          { id: 1, text: "Item1" },
          { id: 2, text: "Item2" },
          { id: 3, text: "Item3" },
          { id: 4, text: "Item4" },
          { id: 5, text: "Item5" },
          { id: 6, text: "Item6" },
        ],
      },
    };
  },
  provide() {
    return {
      provideData: this.provideData,
      deleteItem: this.deleteItem,
    };
  },

  methods: {
    testEvent(data) {
      alert(data);
    },
    deleteItem(todoItem) {
      console.log(todoItem);
      this.provideData.todoList = this.provideData.todoList.filter(
        (t) => t !== todoItem
      );
    },
    addNewTodo(todo) {
      this.provideData.todoList.push({
        id: new Date().getTime(),
        text: todo,
      });
      console.log(todo);
    },
  },
};
</script>
