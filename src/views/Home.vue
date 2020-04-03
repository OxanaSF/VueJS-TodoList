<template>
<div id="app">

<AddTodo v-on:add-todo="addTodo" />
<Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
</div>
</template>

<script>
import Todos from '../components/Todos';
import AddTodo from '../components/AddTodo';
import axios from 'axios';

export default {
name: 'Home',
components: {
Todos,
AddTodo
},
data() {
return {
todos: [
]
}
},
methods: {
deleteTodo(id) {
axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
// eslint-disable-next-line 
.then(res => this.todos = this.todos.filter(todo => todo.id !== id))
.catch(err => console.log(err));

},
addTodo(newTodo) {
const {title, completed } = newTodo;

axios.post('https://jsonplaceholder.typicode.com/todos', {
title,
completed
})
.then(res => this.todos = [...this.todos, res.data])
.catch(err => console.log(err))
this.todos = [...this.todos, newTodo];
}
},
created(){
axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
.then(res => this.todos = res.data)
.catch(err => console.log(err));
}
}
</script>

<style>
#app {
font-family: Avenir, Helvetica, Arial, sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
text-align: center;
color: #856c8b;
margin-top: 60px;
}
.btn {
display: inline-block;
border: none;
background: #856c8b;
color: #ffeb99;
color: fff1c1;
padding: 7px 20px;
cursor: pointer;
font-size: 15px;
}

.btn:hover {
background: #a4c5c6;
}


.router-link-exact-active {
  color: #856c8b;
  }


#app {
  background: #a4c5c6;
}

</style>
