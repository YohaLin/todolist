# todolist
111.06.06 第一次接觸前端框架 Vue

## 作品連結
https://yohalin.github.io/todolist/

## Project setup
```
npm install
```
## 功能介紹
*參考資料習得：<br>
1.新增todo<br>
2.刪除todo<br>
3.編輯todo<br>

## 檔案結構
**assets:**
放入靜態檔案
**components:**
畫面要呈現的元件會放在這邊，如：HTML, CSS, 簡單Javascript
**store:**
state:存放狀態值<br>
getters:由state衍生出的狀態<br>
actions:可以用來呼叫mutations的入口<br>
mutations:存放函式，方便其他檔案方便存入<br>

## Vue 學習過程：
**語法**
### v-bind:id="dynamicId"
notes:透過v-bind可以動態改變HTML的屬性，如：classList
notes: :key裡面要放的是唯一不會重複的值(id)

### v-for="item in items"
notes:迭代功能

###  @my-event="handleThis(123, $event)" 
notes:類似DOM的EventListener

## 參考資料
https://vuejs.org/api/built-in-directives.html<br>
https://github.com/user97116/vue-todo-app<br>
https://github.com/cythilya/todo_list_with_vue_and_vuex<br>
