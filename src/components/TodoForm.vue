<script lang="ts">
import {Options, Vue} from 'vue-class-component';
import {ElMessage} from "element-plus";

@Options({})
export default class TodoForm extends Vue {
  formInput = {title: "", completed: false};

  onSubmit() {
    if (this.formInput.title.length > 3) {
      this.$emit('send-message', this.formInput);
    } else {
      ElMessage({
        message: "Title must be longer than 3 characters",
        type: "error",
      })
    }
    this.formInput.title = "";
  }
}
</script>

<template>
  <el-form :inline="true" :model="formInput" class="todo-form-input" @submit.prevent>
    <el-form-item label="Title" prop="title">
      <el-input v-model="formInput.title" placeholder="Enter Todo"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="onSubmit()">Add</el-button>
    </el-form-item>
  </el-form>
</template>

<style scoped>

</style>