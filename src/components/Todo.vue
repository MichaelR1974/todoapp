<template>
  <div
    class="flex justify-between items-center py-2 px-2"
    :class="{ 'bg-green-600': this.todo.done, 'bg-red-600': !this.todo.done }"
  >
    <h1 class="cursor-pointer" @click="toggleTodo">{{ todo.todo }}</h1>
    <button class="bg-black py-1 py-1 rounded" @click="removeTodo">Delete Todo</button>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Todo",
  props: ["todoprop", "todoindex"],
  data() {
    return {
      todo: this.todoprop,
    };
  },
  methods: {
    toggleTodo() {
      this.$emit("toggledone-index", this.todoindex);
    },
    removeTodo() {
      this.$emit("removetodo-index", this.todoindex);
    },
  },
};
</script>
