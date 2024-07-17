<template>
  <body> 
    <div class="container">
      <section>
        <input type="text" class="input-group" v-model="inputTodo">
        <button @click="addTodo" class="btn-success btn">Add</button>

      </section>

      <ul class="list-group" v-for="todo in todoList" :key="todo.id">
        <li class="list-group-item" v-if="todo !=''">
          {{ todo }}
          <button class="btn btn-danger" @click ="() => deleteTodo(todo)" >
            Delete

          </button>

        </li>
        
      </ul>
    </div>
  </body>
</template>

<script>

export default {
  name: 'App' ,

  data(){
    return {
      inputTodo: '',
      todoList: [''],
  }
},

methods: {
  addTodo() {
    this.todoList.push(this.inputTodo)
    this.inputTodo = ""
  },

  deleteTodo(todo) {
    const index = this.todoList.indexOf(todo)
    if (index > -1) {
      this.todoList.splice(1,index)
    }
  }
}, 

components: {

  }

}

</script>

<style>

</style>


