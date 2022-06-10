<template>
  <div>
    <div class="row">
      <input @change="todoTextChange" v-bind:value="todoText" class="col form-control mx-4" type="text" />
      <button @click="addTodoI" class="col-2 btn-outline-secondary btn-sm">Add</button>
    </div>
  </div>
</template>

<script>
// Vuex的共享狀態管理機制（ Shared State Management ）：可以在不同元件中做溝通(共享資訊)
// mapGetters 可以取得 getters 裡面的方法
import { mapActions } from 'vuex';
import { v1 } from 'uuid'
export default {
  data() {
    return {
      todoText: ""
    };
  },
  // 新增功能：空字串不能新增
  methods: {
    ...mapActions(["addTodo"]),
    todoTextChange(e) {
      // this取到的是data的值喔！
      let value = e.target.value.trim() //新增
      if (value.length <= 0) return //新增
      this.todoText = value; 
    },
    addTodoI() {
      if(this.todoText.length <= 0) return //新增
      this.addTodo({
        id: v1(),
        title: this.todoText
      });
      this.todoText = "";
    }
  }
};
</script>

<style scoped>
</style>
