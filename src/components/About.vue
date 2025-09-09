<template>
  <section class="about">
    <div class="about-container">
      <img src="../assets/profile.jpeg" alt="Aazib" class="about-image" />
      <div class="about-text">
        <h2>About Me</h2>
        <p>
          Hi! My name is Aazib Majeed. I am a Bsc Computer Engineering Graduate from UET Taxila.
          My key areas of interest include Embedded Systems,Machine Learning, and Web development.
          I have done projects in each of these domains and have a fair understanding of each, My main
          area of interest however is Embedded systems as my Final Year Project was in that domain. My main 
          hobby is Video Games.
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


