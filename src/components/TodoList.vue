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
  todos = [];

  async mounted() {
    await this.loadTodos();
  }

  async loadTodos() {
    try {
      const response = await this.axios.get("http://192.168.31.180:8081/api/v1/todos");
      this.todos = response.data;
    } catch (error) {
      console.log('An error occurred:', error);
    }
  }
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
  <el-row>
    <el-col :span="12" :offset="7" style="width: 100%">
      <h1>TodoList</h1>
      <todo-form @send-message="createTodo"></todo-form>
    </el-col>
  </el-row>
</template>

<style scoped>

</style>