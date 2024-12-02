<template>
  <div class="hero-section">
    <div class="hero-content">
      <div class="hero-text">
        <h1 class="hero-title animate__animated animate__fadeIn animate__delay-1s">{{ title }}</h1>
        <p class="hero-description animate__animated animate__fadeIn animate__delay-1.5s">{{ description }}</p>
        <p class="cta-text animate__animated animate__fadeIn animate__delay-2s">{{ ctaText }}</p>
        <nuxt-link to="/about">
      <button class="cta-btn animate__animated animate__fadeIn animate__delay-2.5s">
        Get in Touch
      </button>
    </nuxt-link>  
      </div>
    </div>
  </div>
</template>

<script>
export default {

  data() {
    return {
      title: 'Web Developer',
      description: 'Crafting seamless and engaging web experiences.',
      ctaText: "Let's collaborate and create something amazing!",
    };
  },
};
</script>

<style scoped>
.hero-section {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh;
  background: linear-gradient(135deg, #67272B, #67272B),
    #67272B;
  color: white;
  overflow: hidden;
  padding: 0 20px;
  text-align: center;
  animation: fadeInBackground 2s ease-in-out forwards;
  cursor: pointer;
}


@keyframes fadeInBackground {
  0% {
    background: linear-gradient(135deg, #67272B, #67272B),
    #67272B; 
  }
  100% {
    background: linear-gradient(135deg, #67272B, #67272B),
    #67272B; 
  }
}
.hero-content {
  display: grid;
  place-items: center;
  height: 100%;
  width: 100%;
  z-index: 1;
  transform: translateY(-10px);
  animation: slideIn 2s ease-out forwards;
}

.hero-text {
  max-width: 800px;
  text-align: center;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 20px;
  text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
  animation: floatIn 1.5s ease-in-out forwards;
}

@keyframes floatIn {
  0% {
    opacity: 0;
    transform: translateY(30px) rotateX(45deg);
  }
  100% {
    opacity: 1;
    transform: translateY(0) rotateX(0);
  }
}

.hero-description {
  font-size: 1.5rem;
  margin-bottom: 30px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
  animation: fadeInDescription 2s ease-in-out forwards;
}

@keyframes fadeInDescription {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.cta-text {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 20px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
  animation: fadeInCtaText 2s ease-in-out forwards;
}

@keyframes fadeInCtaText {
  0% {
    opacity: 0;
    transform: translateY(10px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.cta-btn {
  background-color: #f7b731;
  color: #333;
  padding: 12px 30px;
  border: none;
  border-radius: 30px;
  font-size: 1.1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  animation: fadeInButton 2s ease-in-out forwards;
  transform: scale(1);
  animation: bounceIn 1s ease-out forwards;
}

@keyframes bounceIn {
  0% {
    transform: scale(0.7);
    opacity: 0;
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.cta-btn:hover {
  background-color: #f39c12;
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  transition: all 0.2s ease;
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
  .hero-description {
    font-size: 1.2rem;
  }
  .cta-text {
    font-size: 1rem;
  }
  .cta-btn {
    font-size: 1rem;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 2rem;
  }
  .cta-btn {
    padding: 10px 25px;
    font-size: 1rem;
  }
}
</style>
