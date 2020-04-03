<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p class="checkbox">
  <input type="checkbox" v-on:change="markComplete">
  {{todo.title}}
  <button @click="$emit('del-todo', todo.id)" class="del">x</button>
</p>
  </div>
</template>



<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
}
}
}
</script>


<style scoped>
  
  .todo-item {
      background-color: #d4ebd0;
      padding: 10px;
      border-bottom: 1px #a4c5c6 dotted;
  }


  .is-complete {
    text-decoration: line-through;
  }
  .del {
      background-color: #a4c5c6;
      color: #856c8b;
      border: none;
      padding: 5px 9px;
      border-radius: 50%;
      cursor: pointer;
      float: right;
  }



</style>