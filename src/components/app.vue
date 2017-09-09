<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <todos-header :addTodo="addTodo"></todos-header>
      <list :todos="todos" :deleteTodo="deleteTodo"></list>
      <todos-footer></todos-footer>
    </div>
  </div>
</template>

<script>
  import header from './header.vue'
  import list from './list.vue'
  import footer from './footer.vue'

  export default {
    data () {
      return {
        todos: [
          {title: '吃饭1', complete: false},
          {title: '吃饭2', complete: true},
          {title: '吃饭3', complete: false},
          {title: '吃饭4', complete: false}
        ]
      }
    },

    methods: {
      addTodo (todo) {
        this.todos.unshift(todo)
      },

      deleteTodo (index) {
        this.todos.splice(index, 1)
      },

      // 全选/全选
      selectAll (isCheck) {
        this.todos.forEach(todo => {
          todo.complete = isCheck
        })
      },

      // 清除所有已完成的
      clearAllCompleted () {
        this.todos = this.todos.filter(todo => !todo.complete)
      }
    },

    components: {
      'todos-header': header,
      list,
      'todos-footer': footer
    }
  }
</script>

<style>
  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
</style>