<template>
  <div class="container">
    <div class="row my-3 justify-content-between">
      <h3 v-if="!editing" class="col">{{todo.title}}</h3>
      <input v-bind:value="todoText" @change="todoTextChange" v-else type="text" class="col form-control" />
      <div class="col">
        <!-- editing為true：update / false：Edit -->
        <button @click="updateTodoI(todo)" class="btn btn-outline-secondary btn-sm mx-2">{{editing? 'Update':
          'Edit'}}</button>
        <button @click="deleteTodo(todo.id)" class="btn btn-outline-danger btn-sm">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  props: {
    todo: {},
  },
  data(){
    return{
      todoText: "",
      editing: false
    };
  },
  methods: {
    // 映射為 `this.$store.dispatch('deleteTodo', 'updateTodo')`
    ...mapActions(['deleteTodo', 'updateTodo']),
    todoTextChange(e){
      let value = e.target.value.trim() //新增
      if (value.length <= 0) return //新增
      this.todoText = e.target.value;
    },
  updateTodoI(todo) {
    this.editing = this.editing == true ? false : true; 
    if(this.editing) {
      this.todoText = todo.title;
      this.updateTodo(todo);
    }else{
      todo.title = this.todoText;
    }
  }
  }
}
</script>

<style scoped>
</style>
