<script>
import {defineNuxtComponent} from "nuxt/app";

export default defineNuxtComponent({
  data: () => ({
    todoList: []
  }),
  methods: {
    fetchTodoList(){
      fetch('https://jsonplaceholder.typicode.com/todos/')
          .then(response => response.json())
          .then(json => this.todoList = json)
    }
  }
})

</script>


<template>
  <div>
    <h1>Mustafa`s Nuxt</h1>
    <button @click="fetchTodoList"> Click to fetch Data</button>
    <pre>
      {{todoList}}
    </pre>
  </div>
</template>
