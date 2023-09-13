<script lang="ts">
import {Options, Vue} from 'vue-class-component';
import TodoForm from "@/components/TodoForm.vue";

@Options({
  components: {
    TodoForm,
  }
})
export default class TodoList extends Vue {

}
</script>

<template>
  <h1>TodoList</h1>
  <todo-form></todo-form>
</template>

<style scoped>

</style>