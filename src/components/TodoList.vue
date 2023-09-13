<script lang="ts">
import {Options, Vue} from 'vue-class-component';
import TodoForm from "@/components/TodoForm.vue";
import {ElMessage} from "element-plus";

@Options({
  components: {
    TodoForm,
  }
})
export default class TodoList extends Vue {
  async createTodo(todo: any) {
    console.log("Todo", todo)
    ElMessage({
      message: "Todo created",
      type: "success"
    })
  }
}
</script>

<template>
  <h1>TodoList</h1>
  <todo-form @send-message="createTodo"></todo-form>
</template>

<style scoped>

</style>