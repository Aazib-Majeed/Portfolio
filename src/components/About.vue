<template>
  <section class="about">
    <div class="about-container">
      <img src="../assets/profile.jpeg" alt="Aazib" class="about-image" />
      <div class="about-text">
        <h2>About Me</h2>
        <p>
          I love working with Vue.js and building creative web applications.
          My interests include Embedded Systems, Networking, and Web Development.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "About"
}
</script>

<style scoped>
.about-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 30px;
  margin-top: 20px;
}

.about-image {
  width:20%;
  height: 20%;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.about-text {
  max-width: 600px;
}

.about-text h2 {
  margin-bottom: 10px;
}
.about {
  width:100%;
  height: 30%;
}
</style>
