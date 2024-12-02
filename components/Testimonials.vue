<template>
  <div class="testimonials-section py-5" id="testimonials">
    <div class="container">
      <h2 class="text-center mb-5 title-Animation">What Our Clients Say</h2>
      <div class="row justify-content-center">
        <div
          class="col-md-4 col-sm-12 testimonial-card"
          v-for="(testimonial, index) in testimonials"
          :key="index"
        >
          <div class="card shadow-lg testimonial-box" data-aos="fade-up">
            <img
              :src="testimonial.image"
              :alt="testimonial.name"
              class="testimonial-img rounded-circle mx-auto"
            />
            <div class="card-body text-center">
              <h5 class="card-title">{{ testimonial.name }}</h5>
              <p class="card-text">{{ testimonial.text }}</p>
            </div>
            <div class="card-footer text-muted text-center">
              <i class="bi bi-star-fill text-warning"></i>
              {{ testimonial.rating }} / 5
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Testimonials',
  data() {
    return {
      testimonials: [
        {
          name: 'Rohit',
          text: 'Working with this team was a game changer for my business! They took the time to understand my needs and delivered a sleek, professional website that perfectly reflects my brand.They were quick to respond. I couldn’t be happier with the outcome!',
          image: '/img/men1.jpg',
          rating: 5,
        },
        {
          name: 'Sarah Johnson',
          text: 'The service I received exceeded all expectations. From the initial consultation to the final product, the team demonstrated unmatched expertise and attention to detail. My website not only looks fantastic but also performs seamlessly. Highly recommended!',
          image: '/img/women1.jpg',
          rating: 5,
        },
        {
          name: 'John Williams',
          text: 'I am extremely satisfied with the results! The design team listened to my ideas and transformed them into a beautiful, functional website. They were quick to respond, kept me updated throughout the process, and delivered on time. I would definitely work with them again!',
          image: '/img/men2.jpg', 
          rating: 5,
        },
      ],
    };
  },
};
</script>

<style scoped>
.testimonials-section {
  background-color: rgb(191, 167, 138);
  padding: 80px 0;
  position: relative;
}

.section-title {
  font-family: 'Roboto', sans-serif;
  font-size: 2.5rem;
  color: #67272B;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin-bottom: 50px;
  animation: fadeInTitle 1.5s ease-in-out;
}

@keyframes fadeInTitle {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.testimonial-card {
  margin-bottom: 30px;
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease;
}

.testimonial-card:hover {
  transform: translateY(-15px);
  }

.testimonial-box {
  border-radius: 15px;
  overflow: hidden;
  background: linear-gradient(45deg, #797374, #ffafcc);
  position: relative;
  padding: 30px;
}

.testimonial-img {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border: 4px solid #fff;
  margin-top: 5px;
  transition: transform 0.3s ease-in-out;
}

.testimonial-img:hover {
  transform: scale(1.1);
}

.card-body {
  padding: 20px;
}

.card-title {
  font-size: 1.5rem;
  font-weight: bold;
  color: #333;
  transition: color 0.3s ease;
}

.card-title:hover {
  color: #ff6f61;
}

.card-text {
  font-size: 1rem;
  color: #555;
  line-height: 1.6;
  margin-bottom: 15px;
  font-style: italic;
}

.card-footer {
  background-color: #fff;
  font-size: 0.875rem;
  padding: 10px;
  }

.card-footer i {
  margin-right: 5px;
  font-size: 1.2rem;
}

.card-footer .text-muted {
  color: #777;
}

@media (max-width: 767px) {
  .testimonial-img {
    width: 100px;
    height: 100px;
  }

  .section-title {
    font-size: 2rem;
  }

  .card-title {
    font-size: 1.25rem;
  }

  .card-text {
    font-size: 0.9rem;
  }
}

/* Custom animation for cards */
@keyframes fadeInCards {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.testimonial-card {
  animation: fadeInCards 1s ease-in-out;
}

.testimonials-section::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  opacity: 0.1;
  z-index: -1;
}
</style>
