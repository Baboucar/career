<template>
    <section class="testimonial-section">
      <h2 class="testimonial-title">Transforming careers, one success story at a time</h2>
      <button class="all-testimonials-btn">All testimonials</button>
      <div class="testimonial-grid">
        <div class="testimonial-card" v-for="(testimonial, index) in testimonials" :key="index">
          <p class="testimonial-text">“{{ testimonial.text }}”</p>
          <div class="testimonial-author">
            <img :src="testimonial.photo" :alt="testimonial.name" class="author-photo">
            <div>
              <p class="author-name">{{ testimonial.name }}</p>
              <p class="author-title">{{ testimonial.title }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        testimonials: [
          {
            text: "Their comprehensive career assessment helped me identify my strengths and interests, guiding me towards a fulfilling career path. Their expert guidance has been invaluable in my professional development.",
            name: "Brian Davis",
            title: "CMO, Trendsetter Styles",
            photo: "/avatar.jpg"
          },
          {
            text: "Their educational guidance helped me choose the right educational path to achieve my career goals. Their professional development strategies have helped me enhance my skills and achieve my career objectives.",
            name: "Michael Lee",
            title: "Director, The Online Emporium",
            photo:  "/avatar.jpg"
          },
          {
            text: "Career guidance has been a great partner in my career success. Their expert consultants provide customized strategies and guidance to help me navigate the complex world of professional development.",
            name: "Mark Johnson",
            title: "Marketing Director, Acme Solutions",
            photo:   "/avatar.jpg"
          },
          {
            text: "Their supportive and collaborative approach has been instrumental in my career growth. Their expert guidance and comprehensive career assessment have helped me unlock my full potential.",
            name: "Sarah Wilson",
            title: "Founder, Greenly Technologies",
            photo:   "/avatar.jpg"
          }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  .testimonial-section {
    padding: 2rem;
    background-color: #111; /* Adjust to match the background */
    color: #fff;
  }
  
  .testimonial-title {
    font-size: 2rem;
    margin-bottom: 1rem;
  }
  
  .all-testimonials-btn {
    background-color: #3b82f6;
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
    margin-bottom: 2rem;
  }
  
  .testimonial-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .testimonial-card {
    background-color: #1a1a1a; /* Dark background for contrast */
    padding: 1.5rem;
    border-radius: 8px;
  }
  
  .testimonial-text {
    font-size: 1rem;
    margin-bottom: 1.5rem;
  }
  
  .testimonial-author {
    display: flex;
    align-items: center;
  }
  
  .author-photo {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    margin-right: 1rem;
  }
  
  .author-name {
    font-weight: bold;
  }
  
  .author-title {
    font-size: 0.875rem;
    color: #999;
  }
  
  /* Responsive Design */
  @media(min-width: 768px) {
    .testimonial-grid {
      grid-template-columns: repeat(4, 1fr);
    }
  }
  
  @media(min-width: 1024px) {
    .testimonial-grid {
      grid-template-columns: repeat(4, 1fr);
      gap: 2rem;
    }
  }
  </style>
  