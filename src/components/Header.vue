<template>
  <header class="header">
    <h1>Aazib’s Portfolio</h1>

    <!-- use a semantic nav element so the script can find links reliably -->
    <nav class="nav-links" aria-label="Main navigation">
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#Resume">Resume</a>
      <a href="#contact">Contact</a>
    </nav>
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
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
  height: 60px;
}

/* nav link look (scoped) */
.nav-links a {
  text-decoration: none;
  color: white;
  font-weight: 600;
  margin: 0 10px;
  padding: 6px 8px;
  border-radius: 6px;
  transition: background 0.18s, color 0.18s, transform 0.18s;
}

.nav-links a:hover {
  color: #42b983;
  background: rgba(66,185,131,0.05);
}
</style>


