<template>
  <!--组件模板可以直接读取组件对象的属性显示-->
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <item v-for="(comment, index) in comments" :comment="comment" :key="index"></item>
    </ul>
  </div>
</template>

<script>
  import item from './item.vue'

  export default {
    //声明接收属性
    props: ['comments'],  //comments就会成为组件对象的属性

    components: {
      item
    }
  }
</script>

<style>
  .reply {
    margin-top: 0px;
  }
</style>