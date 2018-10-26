<template>
  <div class="TodoItem">
    <p class="TodoItem-Text">{{todo.text}}</p>
    <div class="TodoItem-Delete" @click="deleteItem(todo)"> - </div>
  </div>
</template>
<script>
export default {
  name: 'to-do-item',
  props: ['todo'],
  methods: {
    deleteItem(todo) {
      this.$emit('delete', todo)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.TodoItem{
  display: flex;
  justify-content: center;
  align-items: center;
}
.TodoItem-Text {
  width: 90%;
  background: #fff;
  border: solid 1px #ddd;
  padding: 12px;
  margin-right: 10px;
}
</style>
