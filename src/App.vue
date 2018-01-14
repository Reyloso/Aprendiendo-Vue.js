<template>
  <div id="app">
    <section class="hero is-primary is-bold is-fullheight">
     <!-- Hero head: will stick at the top -->
     <div class="hero-head">
       <nav class="navbar">
         <div class="container">
           <div class="navbar-brand">
             <a class="navbar-item">
               VueJs Pratica
             </a>
           </div>
         </div>
       </nav>
     </div>

     <!-- Hero content: will be in the middle -->
     <div class="hero-body">
         <div class="container has-text-centered">
           <div class="row">
             <div class="columns">
               <div class="column is-half is-offset-one-quarter">
                 <todo-card>
                   <nuevo-todo> </nuevo-todo>
                 </todo-card>
               </div>
             </div>
           </div>
         </div>
       </div>

     <!-- Hero footer: will stick at the bottom -->
     <div class="hero-foot">
       <div class="container">
         <div class="content has-text-centered">
           <p>
             <strong>VueJS Pratica</strong> by <a href="http://github.com/reyloso">Reyloso</a>.
           </p>
         </div>
       </div>
     </div>
   </section>
  </div>
</template>

<script>

import TodoCard from './components/TodoCard'

export default {
  name: 'app',
  components: {
    TodoCard
  },
  data () {
    return {
      msg: 'Hello world'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
