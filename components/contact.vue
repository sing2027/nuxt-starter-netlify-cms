<template>
    <div class="contact-container">
      <section class="contact-header">
        <div class="contact-header-content">
          <h1 class="title">Get in Touch</h1>
          <p class="subtitle">Let's work together! Drop a message, and I'll get back to you ASAP.</p>
        </div>
      </section>
  
      <section class="contact-form">
        <div class="form-container">
          <h2>Contact Me</h2>
          <form class="form">
            <div class="form-group">
              <label for="name">Full Name</label>
              <input type="text" id="name" required />
            </div>
            <div class="form-group">
              <label for="email">Email Address</label>
              <input type="email" id="email" required />
            </div>
            <div class="form-group">
              <label for="message">Your Message</label>
              <textarea id="message" required></textarea>
            </div>
            <button type="submit" class="submit-btn">Send Message</button>
          </form>
        </div>
      </section>
  
      <section class="contact-info  py-5">
  <h2 class="section-title text-center mb-4">Contact Information</h2>
  <div class="row gy-4">
    <div class="col-12 col-md-4 text-center">
      <div class="info-item p-3 border rounded shadow-sm">
        <h3>Phone</h3>
        <p>+1 (613) 799-9441</p>
      </div>
    </div>
    <div class="col-12 col-md-4 text-center">
      <div class="info-item p-3 border rounded shadow-sm">
        <h3>Email</h3>
        <p>Deep_sing@gmail.com</p>
      </div>
    </div>
    <div class="col-12 col-md-4 text-center">
      <div class="info-item p-3 border rounded shadow-sm">
        <h3>Location</h3>
        <p>Ontario, Canada</p>
      </div>
    </div>
  </div>
</section>

  
      <section class="social-media">
        <h2 class="section-title">Follow Me</h2>
        <div class="social-icons">
          <a href="https://linkedin.com/in/your-profile" target="_blank" class="social-icon linkedin">
            <i class="fab fa-linkedin"></i> LinkedIn
          </a>
          <a href="https://github.com/your-profile" target="_blank" class="social-icon github">
            <i class="fab fa-github"></i> GitHub
          </a>
          <a href="https://twitter.com/your-profile" target="_blank" class="social-icon twitter">
            <i class="fab fa-twitter"></i> Twitter
          </a>
        </div>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {};
    },
  };
  </script>
  
  <style scoped>
  
  .contact-container {
    width: 100%;

  }
  
  .contact-header {
    background: #123A3C;
    color: white;
    padding: 80px 20px;
    text-align: center;
    position: relative;
    animation: fadeIn 1s ease-out;
  }
  
  .contact-header-content {
    max-width: 1000px;
    margin: 0 auto;
  }
  
  .title {
    font-size: 3rem;
    font-weight: 700;
    letter-spacing: 1px;
  }
  
  .subtitle {
    font-size: 1.2rem;
    margin-top: 10px;
    opacity: 0.85;
  }
  
  .contact-form {
    padding: 60px 20px;
    background-color: #BFA78A;
  }
  
  .form-container {
    max-width: 800px;
    margin: 0 auto;
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    padding: 30px;
    animation: slideIn 1s ease-out;
  }
  
  .form-container h2 {
    font-size: 2.5rem;
    margin-bottom: 30px;
    color: #00796b;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  .form-group label {
    font-weight: 600;
    color: #00796b;
  }
  
  .form-group input,
  .form-group textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1rem;
  }
  
  .submit-btn {
    width: 100%;
    padding: 12px;
    background-color: #00796b;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1.2rem;
    cursor: pointer;
  }
  
  .submit-btn:hover {
    background-color: #004d40;
  }
  
  .contact-info {
    padding: 60px 20px;
    background-color: #c4b199;
    text-align: center;
    color:white;
  }
  
  .section-title {
    font-size: 2.5rem;
    margin-bottom: 40px;
    color: #00796b;
  }
  
  .info-container {
    display: flex;
    justify-content: space-around;
    gap: 30px;
  }
  
  .social-media {
    padding: 60px 20px;
    background-color: #BFA78A;
    text-align: center;
  }
  
  .social-icons {
    display: flex;
    justify-content: center;
    gap: 30px;
  }
  
  .social-icon {
    font-size: 1.5rem;
    color: #00796b;
    text-decoration: none;
    padding: 12px;
    border-radius: 5px;
  }
  
  .social-icon:hover {
    background-color: #00796b;
    color: white;
  }
  </style>

