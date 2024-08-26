<template>
    <footer class="footer">
      <div class="footer-container">
        <div class="footer-logo">
          <img src="" alt="Company Logo" class="logo" />
          <p class="footer-description">
            Lorem ipsum dolor sit amet consetetur sadipscing elitr sed diam nonumy eirmod tempor invidunt ut labore et.
          </p>
          <div class="social-icons">
            <a href="#" class="social-link"><i class="fab fa-facebook"></i></a>
            <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
            <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
            <a href="#" class="social-link"><i class="fab fa-linkedin"></i></a>
          </div>
        </div>
        <div class="footer-links">
          <h3>Quick Links</h3>
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Programs</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Contacts</a></li>
          </ul>
        </div>
        <div class="footer-links">
          <h3>Explore</h3>
          <ul>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Success Story</a></li>
            <li><a href="#">Membership</a></li>
            <li><a href="#">Purchase Guide</a></li>
            <li><a href="#">Privacy Policy</a></li>
            <li><a href="#">Terms Of Services</a></li>
          </ul>
        </div>
        <div class="footer-contact">
          <h3>Contact Us</h3>
          <p><i class="fas fa-phone-alt"></i> +988 5394 203</p>
          <p><i class="fas fa-envelope"></i> hello@psylo.com</p>
          <p><i class="fas fa-map-marker-alt"></i> 3 Edgar Buildings, George Street, England, BA1 2FJ.</p>
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'Footer'
  }
  </script>
  
  <style scoped>
  .footer {
    background-color:#1f252f;
    color: #ffffff;
    padding: 2rem;
  }
  
  .footer-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 2rem;
  }
  
  .footer-logo {
    flex: 1 1 25%;
  }
  
  .logo {
    width: 120px;
  }
  
  .footer-description {
    margin: 1rem 0;
    font-size: 0.875rem;
    line-height: 1.5;
  }
  
  .social-icons {
    display: flex;
    gap: 1rem;
  }
  
  .social-link {
    color: #ffffff;
    font-size: 1.5rem;
  }
  
  .footer-links {
    flex: 1 1 15%;
  }
  
  .footer-links h3 {
    margin-bottom: 1rem;
    font-size: 1.125rem;
    color: #f2a0a1;
  }
  
  .footer-links ul {
    list-style: none;
    padding: 0;
  }
  
  .footer-links ul li {
    margin-bottom: 0.5rem;
  }
  
  .footer-links ul li a {
    color: #ffffff;
    text-decoration: none;
    font-size: 0.875rem;
    transition: color 0.3s ease;
  }
  
  .footer-links ul li a:hover {
    color: #f2a0a1;
  }
  
  .footer-contact {
    flex: 1 1 25%;
  }
  
  .footer-contact h3 {
    margin-bottom: 1rem;
    font-size: 1.125rem;
    color: #f2a0a1;
  }
  
  .footer-contact p {
    margin: 0.5rem 0;
    font-size: 0.875rem;
  }
  
  .footer-contact i {
    color: #f2a0a1;
    margin-right: 0.5rem;
  }
  
  /* Responsive Design */
  @media (max-width: 768px) {
    .footer-container {
      flex-direction: column;
      align-items: center;
    }
  
    .footer-logo, .footer-links, .footer-contact {
      flex: 1 1 100%;
      text-align: center;
    }
  
    .social-icons {
      justify-content: center;
    }
  }
  </style>
  