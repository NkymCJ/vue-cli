<template>
  <div>
    <AddTodo @add="handleAdd"/>
    <div :key="todo.id" v-for="todo in todos">
      <Todo :todo="todo" @delete="handleDelete(todo.id)"/>
    </div>
  </div>
</template>
<script>
import Todo from '@/components/Todo'
import AddTodo from '@/components/AddTodo'
import uuid from 'uuid'

export default {
  name: 'Todos',
  components: {
    Todo,
    AddTodo
  },
  data () {
    return {
      todos: []
    }
  },
  methods: {
    handleDelete (id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    handleAdd (title) {
      this.todos = [{
        id: uuid.v4(),
        title,
        completed: false
      }, ...this.todos]
    }
  }
}
</script>
<style lang="scss" scoped></style>
