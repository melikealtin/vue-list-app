<template>
  <div>
    <label for="todoText"></label>
    <input
      v-model="todoText"
      @keydown.enter="
        addNewTodo(todoText);
        todoText = '';
      "
      type="text"
      id="todoText"
      placeholder="Bir şeyler yazabilirsiniz..."
    />
  </div>
</template>

<script>
export default {
  props: {
    addNewTodo: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      todoText: null,
    };
  },
};
</script>
