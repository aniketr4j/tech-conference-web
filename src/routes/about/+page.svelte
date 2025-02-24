<script>
  import Navbar from "../../components/Navbar.svelte";
  import Footer from "../../components/Footer.svelte";
  import { onMount } from 'svelte';

  onMount(() => {
    console.log('About page mounted');
  });
</script>

<Navbar />

<section class="about-section">
  <div class="container">
    <h1 class="text-center section-title">About TechConf 2025</h1>
    <p class="lead text-center">
      Welcome to <strong>TechConf 2025</strong>, the ultimate gathering of technology enthusiasts,
      innovators, and industry leaders. This conference serves as a hub for groundbreaking
      discussions, hands-on learning experiences, and unparalleled networking opportunities. Whether
      you're a seasoned professional, entrepreneur, researcher, or student, TechConf is the perfect
      platform for you.
    </p>

    <hr class="styled-divider" />

    <h2 class="section-subtitle">Our Mission</h2>
    <p>
      At TechConf, our mission is to bring together the brightest minds in technology to share
      ideas, foster collaboration, and shape the future of innovation. As technology continues to
      evolve at a rapid pace, we provide a platform for experts and enthusiasts to engage in
      meaningful discussions, gain valuable insights, and stay ahead in this dynamic digital
      landscape.
    </p>

    <hr class="styled-divider" />

    <h2 class="section-subtitle">What to Expect?</h2>
    <div class="row">
      <div class="col-md-6">
        <ul class="features-list">
          <li><strong>🚀 Keynote Sessions:</strong> Insights from global tech leaders & pioneers.</li>
          <li><strong>🛠 Hands-on Workshops:</strong> Learn & explore new tools and frameworks.</li>
          <li><strong>💡 Panel Discussions:</strong> AI, Blockchain, Quantum Computing & Web3.</li>
        </ul>
      </div>
      <div class="col-md-6">
        <ul class="features-list">
          <li><strong>🔬 Innovation Showcase:</strong> Discover emerging startups & disruptors.</li>
          <li><strong>🤝 Networking:</strong> Meet professionals, investors, & recruiters.</li>
          <li><strong>🎯 Career Growth:</strong> Expert guidance, mentorship & job opportunities.</li>
        </ul>
      </div>
    </div>

    <hr class="styled-divider" />

    <h2 class="section-subtitle">Who Should Attend?</h2>
    <div class="row">
      <div class="col-md-6">
        <ul class="features-list">
          <li><strong>👨‍💻 Developers:</strong> Stay updated with the latest programming trends.</li>
          <li><strong>📊 Data Scientists:</strong> Dive into AI, ML, and deep learning.</li>
          <li><strong>💼 Entrepreneurs:</strong> Connect with investors & pitch ideas.</li>
        </ul>
      </div>
      <div class="col-md-6">
        <ul class="features-list">
          <li><strong>🔐 Cybersecurity Experts:</strong> Explore security & cloud solutions.</li>
          <li><strong>🎓 Students:</strong> Gain industry insights & start your tech career.</li>
        </ul>
      </div>
    </div>

    <hr class="styled-divider" />

    <h2 class="section-subtitle text-center">Join the Tech Revolution!</h2>
    <p class="text-center">
      Be part of <strong>TechConf 2025</strong>, where knowledge meets innovation and connections
      turn into opportunities. Whether you're here to learn, collaborate, or showcase your ideas,
      this conference will empower you to make an impact in the tech world.
    </p>

    <div class="event-details text-center">
      <p><strong>📅 Date:</strong> June 15-17, 2025</p>
      <p>
        <strong>📍 Location:</strong>
        <a href="/" target="_blank">
          Bangalore International Exhibition Centre (BIEC), Bangalore
        </a>
      </p>
      <p>
        <strong>📍 Address:</strong> 10th Mile, Tumkur Road, Madavara Post, Dasanapura Hobli, Bangalore,
        Karnataka 562123, India
      </p>
      <p>
        <strong>
          🗺️ <a href="https://www.google.com/maps/dir/?api=1&destination=13.0706368,77.4797703" target="_blank">View on Google Maps</a>
        </strong>
      </p>
      <p>
        <strong>
          🎟️
          <a href="/register" class="btn register-btn">Register Now</a>
        </strong>
      </p>
    </div>
  </div>
</section>

<Footer />

<style>
  .about-section {
    background: linear-gradient(135deg, rgba(0, 0, 50, 0.8), rgba(0, 50, 100, 0.8)),
      url('https://source.unsplash.com/1600x900/?technology,conference') center/cover no-repeat;
    color: white;
    padding: 80px 0;
    min-height: 100vh;
    font-family: 'Poppins', sans-serif;
    box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.2);
  }

  .section-title, .section-subtitle, .lead, .features-list, .event-details p {
    color: white;
  }

  .styled-divider {
    background: #ffcc00;
  }

  .event-details {
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(5px);
    border-radius: 12px;
    padding: 30px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .event-details:hover {
    transform: scale(1.02);
    box-shadow: 0 6px 12px rgba(255, 255, 255, 0.3);
  }

  .event-details a {
    color: #ffcc00;
    font-weight: bold;
  }

  .register-btn {
    color: white;
    font-weight: bold;
    font-size: 1.3rem;
    padding: 14px 28px;
    border-radius: 6px;
    text-transform: uppercase;
    transition: all 0.3s ease-in-out;
    display: inline-block;
    box-shadow: 0px 3px 10px rgba(255, 204, 0, 0.4);
  }

  .register-btn:hover {
    background-color: #e6b800;
    transform: scale(1.05);
    box-shadow: 0px 5px 15px rgba(255, 204, 0, 0.6);
  }
</style>
