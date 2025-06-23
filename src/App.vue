<template>
  <div id="app">
    <header>
      <nav>
        <router-link to="/">Home</router-link> |
        <router-link to="/about">Sobre</router-link>
      </nav>
    </header>
    <main>
      <router-view />
    </main>
    <footer>
      <p>© 2023 Meu Site Vue</p>
    </footer>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;
}

nav {
  padding: 20px;
  background-color: #42b983;
}

nav a {
  font-weight: bold;
  color: white;
  margin: 0 10px;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #35495e;
}

main {
  min-height: 80vh;
  padding: 20px;
}

footer {
  padding: 20px;
  background-color: #f0f0f0;
}
</style>
