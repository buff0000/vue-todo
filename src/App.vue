<template>
  <div>
    <h1>TodoList</h1>
    <input type="text" v-model="content" />
    <button @click="addTodo">添加</button>
    <ul>
      <li v-for="item of todoData" :key="item.id">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
import './assets/styles/global.styl'

export default {
  name: 'App',
  data() {
    return {
      todoData: ['todo1', 'todo2', 'todo3'],
      content: ''
    }
  },
  methods: {
    addTodo() {
      if (this.content === '') return

      this.todoData.push(this.content)
      this.content = ''
    }
  }
}
</script>

<style lang="stylus" scoped>
li:nth-of-type(odd)
  color: blue
</style>