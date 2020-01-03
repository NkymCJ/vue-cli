<template>
  <div class="todo flex justify-between align-center">
    <div class="text" :class="{'is-complete':todo.completed}">
      <input type="checkbox" @change="markComplete" />
      {{todo.title}}
    </div>
    <button class="del" @click="$emit('delete',todo.id)">x</button>
  </div>
</template>
<script>
export default {
  name: 'Todo',
  props: ['todo'],
  methods: {
    markComplete () {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>
<style lang="scss" scoped>
.todo {
  background: #f4f4f4;
  padding: 0 10px;
  height: 40px;
  border-bottom: 1px #ccc dotted;
  overflow: hidden;

  .text {
    flex: 1;
    &.is-complete {
      text-decoration: line-through;
    }
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    cursor: pointer;
  }
}
</style>
