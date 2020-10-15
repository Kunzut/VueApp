<template>
  <li>
    <span v-bind:class="{done: todo.completed}">
      <input type="checkbox" class="item-input" v-on:change="todo.completed = !todo.completed">
      <strong class="item-id">{{index + 1}}</strong>
      {{todo.title | uppercase}}
    </span>
    <button class="item-btn-delete" v-on:click="$emit('remove-todo', todo.id)">
      &times;
    </button>
  </li>
</template>

<script>

export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: Number,
  },
  filters: {
    uppercase(value) {
      return value.toUpperCase()
    }
  }
}
</script>

<style scoped>
  li {
    border: 1px solid #000;
    padding: 10px;
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
  }

  .item-id {
    margin-right: 10px;
  }

  .item-input {
    margin-right: 10px;
  }

  .item-btn-delete {
    background: red;
    color: #fff;
    font-weight: bold;
    border: 1px solid #000;
    border-radius: 50%;
    outline: none;
  }

  .done {
    text-decoration: line-through;
  }
</style>