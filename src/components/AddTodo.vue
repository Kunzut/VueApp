<template>
  <form @submit.prevent="onSubmit">
    <input
        type="text"
        class="addInput"
        placeholder="add todo"
        v-model="title"
    >
    <button type="submit" class="addBtn">Create</button>
  </form>
</template>

<script>

export default {
  data() {
    return {
      title: ''
    }
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        const newTodo = {
          id: Math.random() * 10,
          title: this.title,
          completed: false
        }

        this.$emit('add-todo', newTodo)

        this.title = ''
      }
    }
  }
}
</script>

<style>
  form {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .addInput {
    width: 75%;
    font-size: 1rem;
    outline: none;
    padding: 5px 15px;
    border: 1px solid #000;
    border-radius: 10px;
  }

  .addBtn {
    font-weight: bold;
    font-size: 14px;
    color: #000;
    background: #4dafe5;
    padding: 10px 15px;
    border: 1px solid #000;
    border-radius: 10px;
    outline: none;

  }
</style>