<template>
  <div class="">
    <h1>Todos</h1>

    <div v-for="todo in todos" :key="todo.id">
      <h3 v-if="todo.url">
        <a :href="todo.url">{{ todo.title }}</a>
      </h3>
      <h3 v-else>{{ todo.title }}</h3>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import todos from "@/views/todos.json";

@Component
export default class Todo extends Vue {
  todos = null;
  todosFake = todos;

  mounted() {
    fetch("https://thomasjwilliam.github.io/data/todos.json")
      .then(response => response.json())
      .then(data => {
        this.todos = data;
      });
  }
}
</script>

<style lang="scss"></style>
