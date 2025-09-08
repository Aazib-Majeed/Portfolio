<template>
  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <div class="contact-container">
      <!-- Left: Contact Form -->
      <div class="c-left">
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
        <h3>Socials</h3>
        <ul class="social-links">
          <li class="s-link"><a href="https://github.com/yourusername" target="_blank">GitHub</a></li>
          <li class="s-link"><a href="https://linkedin.com/in/yourusername" target="_blank">LinkedIn</a></li>
          <li class="s-link"><a href="mailto:your@email.com">Email</a></li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Contact",
};
</script>

