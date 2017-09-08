<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <add></add>
      <list :comments="comments"></list>
    </div>
  </div>
</template>

<script>
  import add from './add.vue'
  import list from './list.vue'

  export default {

    data () {
      return {
        comments: [
          {name: 'Tom', content: 'Vue还不错'},
          {name: 'Jack', content: 'Vue真不错'}
        ]
      }
    },

    components: {
      add, list
    }
  }
</script>

<style>

</style>