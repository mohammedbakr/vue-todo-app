<template>
  <div class="todo-item"
    :class="{'is-completed': todo.completed}"
  >
    <p>
      <input type="checkbox" class="mr-2" @click="todo.completed = !todo.completed">
      {{todo.title}}
      <button class="del" @click="delTodo">x</button>
      </p>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    delTodo() {
      this.$emit('delTodo', this.todo.id);
    }
  }
};
</script>

<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }

  .is-completed {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>