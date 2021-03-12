<template>
  <div class="">
    <h1>Todos</h1>

    <div v-for="todo in todos" :key="todo.id">
      <h3 v-if="todo.source">
        <a :href="todo.source">{{ todo.title }}</a>
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
  todos: Array<any> = [];
  todosFake = todos;

  mounted() {
    // fetch("https://thomasjwilliam.github.io/data/todos.json")
    //   .then(response => response.json())
    //   .then(data => {
    //     this.todos = data;
    //   });

    const url = "https://spreadsheets.google.com/feeds/list/1hrgkcJVAvE6ApOX-F0s0tsw2hWUe8OQFeHcl52TgYBc/od6/public/values?alt=json";
    const url2 = "https://spreadsheets.google.com/feeds/list/2PACX-1vSMa3Z8-ytmYHW_5qsaqFmI28660FkYDGZZEdi974JvMvFsn-vccS3fiJ8vI8P6MFsRZCW2GlvG8BPS/od6/public/values?alt=json";
    // 2PACX-1vSMa3Z8-ytmYHW_5qsaqFmI28660FkYDGZZEdi974JvMvFsn-vccS3fiJ8vI8P6MFsRZCW2GlvG8BPS

    fetch(url)
      .then(response => response.json())
      .then(data => {
        const output = [];
        const entries = data.feed.entry;
        // console.log(entries);
        for (const entry of entries) {
          output.push({
            id: entry.gsx$id.$t,
            title: entry.gsx$title.$t,
            source: entry.gsx$source.$t
          });
        }
        // console.log(output);
        this.todos = output;
      });
  }
}
</script>

<style lang="scss"></style>
