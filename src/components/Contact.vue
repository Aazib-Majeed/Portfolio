<template>
  <section id="contact" class="contact">
   
    <div class="contact-container">
      <!-- Left: Contact Form -->
      <div class="c-left">
         <h2>Contact Me</h2>
        <form>
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" placeholder="Enter your name" required />
          </div>

          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" placeholder="Enter your email" required />
          </div>

          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" rows="5" placeholder="Write your message" required></textarea>
          </div>

          <button type="submit">Send</button>
        </form>
      </div>

      <!-- Right: Socials -->
      <div class="c-right">
        <h2>Socials</h2>
        <div class="social-buttons">
          <a href="https://github.com/Aazib-Majeed" target="_blank" class="social-btn">
            <img src="../assets/Contact/github.png" alt="GitHub" /> GitHub
          </a>
          <a href="www.linkedin.com/in/aazib-majeed-987595351" target="_blank" class="social-btn">
            <img src="../assets/Contact/linkedin.png" alt="LinkedIn" /> LinkedIn
          </a>
          <a href="mailto:aazibmajeed671@gmail@gmail.com" class="social-btn">
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
export default {
  name: "Contact",
};
</script>


