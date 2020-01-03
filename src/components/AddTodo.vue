<template>
  <div class="add-todo">
    <form @submit.prevent="addTodo">
      <input v-model="title" type="text" name="title" placeholder="请添加待办事项..." />
      <input type="submit" value="添加" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  data () {
    return {
      title: ''
    }
  },
  methods: {
    addTodo () {
      // 注册事件
      this.$emit('add', this.title)
      this.title = ''
    }
  }
}
</script>

<style lang="scss" scoped>
.add-todo {
  form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }

  input[type="submit"] {
    flex: 2;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }
}
</style>
