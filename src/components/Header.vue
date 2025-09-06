<template>
  <header class="header">
    <h1>Aazib’s Portfolio</h1>
    <p class="nav-links">
      <a href="#projects">Projects</a> |
      <a href="#skills">Skills</a> |
      <a href="#contact">Contact</a>
    </p>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
.header {
  color: white;
  text-align: center;
  padding: 20px;
}

.nav-links a {
  text-decoration: none;
  color: white;
  font-weight: bold;
  margin: 0 10px;
}

.nav-links a:hover {
  color: #42b983; /* Vue green highlight */
}
</style>
