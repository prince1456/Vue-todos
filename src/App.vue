<template>
  <div id="app">
    <!-- <MyCustomComponent name="Ali Alizada" /> -->
    <Todos v-bind:todos='todos' v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
// import MyCustomComponent from './components/MyNewComponent.vue'
export default {
  name: 'app',
  components: {
    Todos,
  },
   data() {
    return {
     books: 1,
     todos: [
       {
         id: 1,
         title: 'go to Shopping',
         completed: false
       },
        {
         id: 2,
         title: 'practice codes',
         completed: true
       },
        {
         id: 3,
         title: 'send money',
         completed: false
       }
     ]
    }
  },
  methods: {
  deleteTodo(id){
      this.todos = this.todos.filter(todo=>  todo.id !== id)
    }
  },
  beforeCreate() {
    alert('beforCreate hook has been called');
    console.log('beforCreate hook has been called');
 },
 created() {
  alert('Created hook has been called');
  console.log(`books is of type ${typeof this.books}`);
 },
 beforeMount() {
    alert('beforeMount is called')
  },
    mounted(){
    this.$data.hello= 'lalalalallalalalalaalal';
 },
  beforeUpdate(){
    alert('beforeUpdate hook has been called');
  },
  updated(){
    alert('Updated hook has been called');
  },
 beforeDestroy() {
    this.books = null
    delete this.books
  },
  destroyed() {
    this.$destroy() 
    console.log(this)
  }

}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
