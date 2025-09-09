<template>
  <section id="contact" class="contact">
    <div class="contact-container">
      <!-- Left: Contact Form -->
      <div class="c-left">
        <h2>Contact Me</h2>
        <form @submit.prevent="sendEmail">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" v-model="name" placeholder="Enter your name" required />
          </div>

          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" v-model="email" placeholder="Enter your email" required />
          </div>

          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" v-model="message" rows="5" placeholder="Write your message" required></textarea>
          </div>

          <button type="submit">Send</button>
        </form>

        <!-- Feedback message -->
        <p v-if="statusMessage" :class="statusClass">{{ statusMessage }}</p>
      </div>

      <!-- Right: Socials -->
      <div class="c-right">
        <h2>Socials</h2>
        <div class="social-buttons">
          <a href="https://github.com/Aazib-Majeed" target="_blank" class="social-btn">
            <img src="../assets/Contact/github.png" alt="GitHub" /> GitHub
          </a>
          <a href="https://www.linkedin.com/in/aazib-majeed-987595351" target="_blank" class="social-btn">
            <img src="../assets/Contact/linkedin.png" alt="LinkedIn" /> LinkedIn
          </a>
          <a href="mailto:aazibmajeed671@gmail.com" class="social-btn">
            <img src="../assets/Contact/gmail.png" alt="Gmail" /> Gmail
          </a>
          <a href="mailto:tenja135@outlook.com" class="social-btn">
            <img src="../assets/Contact/outlook.png" alt="Outlook" /> Outlook
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  name: "Contact",
  data() {
    return {
      name: "",
      email: "",
      message: "",
      statusMessage: "",
      statusClass: ""
    };
  },
  methods: {
    async sendEmail() {
      try {
        await emailjs.send(
          "service_8b9e1k6",   // replace with your Service ID
          "template_4jgzn9u",  // replace with your Template ID
          {
            title: "Portfolio Contact Form", 
            name: this.name,
            email: this.email,
            message: this.message
          },
          "hj-EEYdNv_ApVC8X0"    // replace with your Public Key
        );

        this.statusMessage = "✅ Message sent successfully!";
        this.statusClass = "success";
        this.name = "";
        this.email = "";
        this.message = "";
      } catch (error) {
        this.statusMessage = "❌ Failed to send message. Please try again.";
        this.statusClass = "error";
        console.error("EmailJS Error:", error);
      }
    }
  }
};
</script>

<style scoped>
.success {
  color: #42b983;
  margin-top: 10px;
}
.error {
  color: #ff4444;
  margin-top: 10px;
}
</style>
