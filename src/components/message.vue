<template>
  <div>
    <ul>
      <li v-for="m in messages">
        <router-link :to="`???/${m.id}`">{{m.title}}</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        messages: []
      }
    },

    mounted () {
      // 模拟发送ajax请求, 异步获取数据
      setTimeout(() => {
        this.messages = [
          {id: 1, title: 'message01'},
          {id: 3, title: 'message03'},
          {id: 5, title: 'message05'}
        ]
      }, 2000)
    }
  }
</script>

<style>

</style>