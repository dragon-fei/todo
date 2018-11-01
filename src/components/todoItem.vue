<template>

  <li class="todo-item" @click="delTodo">{{content}}</li>

</template>

<script>
export default {
  props: ['content','index'],
  methods: {
    delTodo(){
      this.$emit('deleteTodoList',this.index)
    }
  }

}
</script>

<style scoped>
  .todo-item{
    color: red;
  }
</style>
