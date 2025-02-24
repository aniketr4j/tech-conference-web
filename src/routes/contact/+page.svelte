<script>
  import Navbar from "../../components/Navbar.svelte";
  import Footer from "../../components/Footer.svelte";
</script>

<Navbar />

<div class="container my-5 contact-container">
  <h2 class="text-center">Contact Us</h2>
  <form class="contact-form">
    <div class="mb-3">
      <label class="form-label" for="name">Name</label>
      <input type="text" id="name" class="form-control" placeholder="Enter your name" required />
    </div>
    <div class="mb-3">
      <label class="form-label" for="email">Email</label>
      <input type="email" id="email" class="form-control" placeholder="Enter your email" required />
    </div>
    <div class="mb-3">
      <label class="form-label" for="message">Message</label>
      <textarea id="message" class="form-control" placeholder="Write your message" rows="4" required></textarea>
    </div>
    <div class="text-center">
      <button type="submit" class="btn btn-primary">Send</button>
    </div>
  </form>

  <!-- Social Media Links -->
  <div class="social-media text-center mt-4">
    <h5>Follow us on</h5>
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <a href="https://twitter.com/TechConf2025" target="_blank" class="social-icon"><i class="bi bi-twitter"></i></a>
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <a href="https://linkedin.com/company/TechConf2025" target="_blank" class="social-icon"><i class="bi bi-linkedin"></i></a>
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <a href="https://facebook.com/TechConf2025" target="_blank" class="social-icon"><i class="bi bi-facebook"></i></a>
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <a href="https://instagram.com/TechConf2025" target="_blank" class="social-icon"><i class="bi bi-instagram"></i></a>
  </div>
</div>
<Footer/>

<style>
  /* Background Gradient for Consistency */
  /* body {
    background: linear-gradient(135deg, #e3f2fd, #f0f4f8);
  } */

  /* Contact Section - Glassmorphism Effect */
  .contact-container {
    max-width: 600px;
    margin: auto;
    padding: 40px;
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(12px) saturate(1.2);
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    border: 1px solid rgba(255, 255, 255, 0.3);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .contact-container:hover {
    transform: scale(1.02);
    box-shadow: 0 6px 14px rgba(0, 0, 0, 0.2);
  }

  /* Contact Form Fields */
  .contact-form {
    padding: 20px;
  }

  .form-control {
    border-radius: 8px;
    border: 1px solid rgba(0, 0, 0, 0.1);
    padding: 12px;
    font-size: 1rem;
    background: rgba(255, 255, 255, 0.8);
    backdrop-filter: blur(5px);
    box-shadow: inset 0px 2px 5px rgba(0, 0, 0, 0.05);
    transition: all 0.3s ease;
  }

  .form-control:focus {
    border-color: #007bff;
    box-shadow: 0px 0px 8px rgba(0, 123, 255, 0.3);
  }

  /* Submit Button */
  .btn-primary {
    width: 100%;
    padding: 12px;
    font-size: 18px;
    font-weight: bold;
    background: #ff5722;
    border: none;
    color: #fff;
    border-radius: 8px;
    text-transform: uppercase;
    transition: all 0.3s ease-in-out;
    box-shadow: 0px 3px 10px rgba(255, 87, 34, 0.4);
  }

  .btn-primary:hover {
    background: #e64a19;
    transform: scale(1.05);
    box-shadow: 0px 5px 15px rgba(255, 87, 34, 0.6);
  }

  /* Social Media Icons */
  .social-media {
    margin-top: 20px;
  }

  .social-icon {
    font-size: 24px;
    margin: 0 10px;
    color: #007bff;
    text-decoration: none;
    transition: transform 0.3s ease, color 0.3s ease;
  }

  .social-icon:hover {
    transform: scale(1.2);
    color: #0056b3;
  }

  /* Headings */
  h2 {
    font-size: 2.2rem;
    font-weight: bold;
    color: #2c3e50;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
  }

  h5 {
    font-size: 1.5rem;
    color: #37474f;
  }
</style>
