<template>
  <div id="app" class="container">
    <!-- 合法的 JavaScript 屬性名，可以被當作 Vue 元件的名稱，為了避免與現有或未來的標籤名稱產生衝突， 通常會以兩個以上的單字來進行命名 -->
    <TodoInput />
    <TodoList />
  </div>
</template>

<script>
// 透過 import 的方式將外部檔案引入子元件
import TodoInput from '@/components/TodoInput';
import TodoList from '@/components/TodoList';

export default {
  name: 'App',
  components: {
    TodoInput,
    TodoList,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
