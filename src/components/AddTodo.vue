<template>
  <div class="form-group d-flex mt-2">
      <input
        type="text"
        class="form-control m-1"
        name="title"
        placeholder="Add Todo"
        v-model="title"  
      />
      <input
        type="submit"
        class="btn btn-dark m-1"
        value="Add"
        @click.prevent="addTodo"
      />
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo() {
      const newTodo = {
        id: uuidv4(),
        title: this.title,
        completed: false
      };
      // send to parent
      if (this.title) {
        this.$emit('addTodo', newTodo);
      }
      this.title = '';
    }
  }
};
</script>

<style scoped>

</style>