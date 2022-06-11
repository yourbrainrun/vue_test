<template>
  <div id="app">
    <div>
      <input v-model='inputValue'/>
      <button @click="handleSubmit">submit</button>
    </div>
    <ul>
      <todo-item v-for="(item, index) of list" :key="index"
      :content="item"
      :index="index"
      @delete="deleteItem"
      ></todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components: {
    'todo-item': TodoItem
  },
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    deleteItem (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>

</style>
