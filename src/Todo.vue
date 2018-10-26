<template>
  <div id="app">
    <h3>todo list</h3>
    <TodoItem v-for="todo in list"
              :todo="todo"
              @delete="onDeleteItem"
              :key="todo.id"
    />
    <input type="text" v-model="todo" v-on:keyup.enter="createNewToDoItem"/>
    <div class="Todo-add" @click="createNewTodoItem"> + </div>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'todo',
  data() {
    return {
      list: [
        {
          'text': 'chean the house',
        },
        {
          'text': 'wash the dash',
        }
      ],
      todo: ''
    }
  },
  methods: {
    createNewTodoItem () {
      this.list.push({
        'text': this.todo
      })
      this.todo = ''
    },
    onDeleteItem(todo) {
      this.list = this.list.filter(item=> item !== todo)
    }
  },
  components: {
    TodoItem
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
