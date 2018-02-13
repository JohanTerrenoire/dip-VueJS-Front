<template>
  <div>
  <h2>Il y a {{ count }}  tâche(s)</h2>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
      <input class="toggle" type="checkbox" :checked="todo.isDone">
        {{ todo.label }}
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  name: `Todos`,
  data() {
    return {
      todos: [],
    };
  },
  computed: {
    count() {
      return this.$store.getters.count;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  // display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
