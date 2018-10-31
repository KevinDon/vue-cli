<template>
  <div id="app">
    <input type="text" v-model="inputValue">
    <button v-on:click="handleSubmit">提交</button>
    <todo-item v-for="(item, index) of list" v-bind:content="item" v-bind:key="index" v-bind:index="index" v-on:delete="handleDelete"></todo-item>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components: {
    'todo-item': TodoItem
  },
  data: function () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit: function () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete: function (index) {
      this.list.splice(index)
    }
  }
}
</script>

<style>

</style>
