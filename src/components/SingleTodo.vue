<template>
  <div
    class="flex justify-between items-center py-2 px-2"
    :class="{ 'bg-green-600': this.todo.done, 'bg-red-600': !this.todo.done }"
  >
    <h1 class="cursor-pointer" @click="toggleTodo">{{ todo.todo }}</h1>
    <button class="bg-black py-1 px-1 rounded" @click="removeTodo">
      Delete ToDo
    </button>
  </div>
</template>

<script>
export default {
  name: "SingleTodo",
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
