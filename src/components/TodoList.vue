<script lang="ts">
import {Options, Vue} from 'vue-class-component';
import TodoForm from "@/components/TodoForm.vue";
import {ElMessage} from "element-plus";

interface Todo {
  id: number;
  title: string;
  completed: boolean;
}

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
      const response = await this.axios.get("http://localhost:8081/api/v1/todos");
      this.todos = response.data;
    } catch (error) {
      console.log('An error occurred:', error);
    }
  }

  async createTodo(todo: any) {
    console.log("Todo", todo)
    await this.axios.post("http://localhost:8081/api/v1/todos", {
      title: todo.title,
      completed: todo.completed,
    });
    ElMessage({
      message: "Todo created",
      type: "success",
    });
    await this.loadTodos();
  }

  async updateTodo(todo: Todo) {
    console.log("Todo", todo)
    await this.axios.put(`http://localhost:8081/api/v1/todos/${todo.id}`, {
      id: todo.id,
      title: todo.title,
      completed: todo.completed,
    });
    ElMessage({
      message: "Todo updated",
      type: "success",
    });
    await this.loadTodos();
  }

  async deleteTodoById(todo: Todo) {
    await this.axios.delete(`http://localhost:8081/api/v1/todos/${todo.id}`);
    ElMessage({
      message: "Todo deleted",
      type: "success",
    });
    await this.loadTodos();
  }

  cancelDelete() {
    console.log("Canceled the delete")
  }
}
</script>

<template>
  <el-row>
    <el-col>
      <h1>TodoList</h1>
      <todo-form @send-message="createTodo"></todo-form>
      <el-table :data="todos">
        <el-table-column label="Title" prop="title"></el-table-column>
        <el-table-column fixed="right" label="Operations">
          <template #default="scope">
            <el-space wrap>
              <el-switch v-model="scope.row.completed" @change="updateTodo(scope.row)"></el-switch>
              <el-popconfirm cancel-button-text="No" confirm-button-text="Yes" icon="el-icon-info" icon-color="red"
                             title="Are you sure to delete this todo?"
                             @cancel="cancelDelete"
                             @confirm="deleteTodoById(scope.row)">
                <template #reference>
                  <el-button size="small" type="danger">Delete</el-button>
                </template>
              </el-popconfirm>
            </el-space>
          </template>
        </el-table-column>
      </el-table>
    </el-col>
  </el-row>
</template>

<style scoped>

</style>