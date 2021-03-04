<template>
  <div class="todo">
    <h1>Todos</h1>

    <ul>
      <li>Eat with fingers</li>
      <li>Walk Santiago de Compostela</li>
      <li>Marte - El espejo rojo</li>
    </ul>
  </div>
</template>

<script lang="ts">

import {Component, Prop, Vue} from "vue-property-decorator";

@Component
export default class Todo extends Vue {
  mounted() {
    console.log('mounted');
    // http://thomasjwilliam.github.io/data/todos.json
    fetch("http://thomasjwilliam.github.io/data/todos.json", {
      mode: "no-cors" // 'cors' by default
    }).then(data => console.log(data));
  }
}
</script>

<style lang="scss"></style>
