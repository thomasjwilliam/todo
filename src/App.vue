<template>
  <div id="app" class="flex column gaps">
    <div id="nav" class="box">
      <router-link to="/">Todos</router-link> |
      <router-link to="/style">Style</router-link>
    </div>
    <main class="box grow">
      <router-view class="" />
    </main>
    <div class="box">
      <a href="https://github.com/thomasjwilliam/data/blob/main/todos.json"
        >Github data source</a
      > |
      <a href="https://docs.google.com/spreadsheets/d/1hrgkcJVAvE6ApOX-F0s0tsw2hWUe8OQFeHcl52TgYBc/edit#gid=0"
        >Sheets data source</a
      >
    </div>
  </div>
</template>

<style>
html,
body {
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
}

#nav {
  /*padding: 30px;*/
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

main {
  /*display: flex;*/
  /*flex-flow: row wrap;*/
  /*align-items: flex-start;*/
}
</style>
