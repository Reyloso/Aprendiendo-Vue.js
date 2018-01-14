<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title has-text-left">
      Dia  {{dia}}
      </p>
      <div class="has-text-right">
        <p class="card-header-title">{{tareas.length}} </p>
      </div>
    </header>
    <div class="card-content">
      <div class="content">  <nuevo-todo @nuevaTarea="adicionarTarea"> </nuevo-todo></div>
      <div class="content"><todo-list :tareas="tareas" @check="checkTarea" @remover="removerTarea"> </todo-list></div>
    </div>
  </div>
</template>

<script>

import nuevoTodo from './nuevoTodo'
import todoList from './todoList'

export default {
  name: 'todo-card',
  components: {
    nuevoTodo,
    todoList
  },
  data () {
    return {
      dias: ['Domingo', 'Lunes', 'Martes', 'Miercoles', 'Jueves', 'Viernes', 'Sábado'],
      meses: ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Septiembre', 'Octubre', 'Noviembre', 'Diciembre'],
      tareas: []
    }
  },
  computed: {
    dia: function() {
      let novaData = new Date()
      return `${this.dias[novaData.getDay()]}, ${novaData.getDate()} de ${this.meses[novaData.getMonth()]}`
    }
  },
  methods: {
    adicionarTarea(tarea) {
      let nova_tarea = {'description': tarea, 'checked': false}
      this.tareas.push(nova_tarea)
    },
    checkTarea(index) {
      this.tareas[index]['checked'] = !this.tareas[index]['checked']
    },
    removerTarea(index){
      this.tareas.splice(index,1)
    }
  }
}
</script>

<style>
.card {
  border-radius: 10px;
}
.card-header-title {
  color: #636368;
}
</style>
