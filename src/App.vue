<template>
  <div id="app">
    <div id="container">
      <AddTodo/>
      <FilterTodos/>
      <Todos/>
    </div>
  </div>
</template>

<script>
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'
import FilterTodos from './components/FilterTodos'
export default {
  name: 'app',
  components: {
    Todos,
    AddTodo,
    FilterTodos
  }
}
</script>

<style>
body {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  line-height: 1.6;
  background: #38f7f0;
}
.container {
  margin: auto;
  overflow: auto;
  padding: 0 2rem;
  max-width: 1100px;
}
</style>
