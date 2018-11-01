<template>
  <div>
    <div>
      <input v-model="inputvalue"/>
      <button @click="handelTodoList">提交</button>
    </div>
    <ul>
      <todo-item v-for="(item,index) of list" :key="index" :content="item" :index="index" @deleteTodoList="delList">{{content}}</todo-item>
    </ul>
  </div>
</template>

<script>
import todoItem from './components/todoItem'
export default {
 components: {
    'todo-item': todoItem
 },
 data(){
      return {
        inputvalue: 'abc',
        list: []
      }
      
  },
  
  methods: {
    handelTodoList(){
      this.list.push(this.inputvalue);
      this.inputvalue = '';
    },
    delList(index){
      this.list.splice(index,1);
    }
  }
  
}
</script>

<style scoped>

</style>
