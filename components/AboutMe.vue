<template>
  <div class="about-me-section py-5">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-4 text-center mb-4">
          <div class="profile-image-container">
            <img
              src="/img/Deep_sing.jpg"
              alt="Profile Picture"
              class="img-fluid rounded-circle shadow-lg profile-img"
            />
          </div>
        </div>
        <div class="col-md-8">
          <h2 class="text-center mb-4 title-Animation">About Me</h2>
          <p class="lead text-center mb-5 about-me-description">
            Hello, I'm <strong>Deep Sing</strong>, a passionate Web Developer, Graphic Designer, and UX Specialist with a strong focus on creating seamless and engaging digital experiences.
          </p>
          <h3 class="h5 skill-title-Animation text-center">Skills & Technologies</h3>
          <ul class="list-inline skills-list">
            <li class="list-inline-item badge bg-primary skill-item">HTML</li>
            <li class="list-inline-item badge bg-success skill-item">CSS</li>
            <li class="list-inline-item badge bg-warning skill-item">JavaScript</li>
            <li class="list-inline-item badge bg-info skill-item">Vue.js</li>
            <li class="list-inline-item badge bg-danger skill-item">Node.js</li>
            <li class="list-inline-item badge bg-dark skill-item">Nuxt.js</li>
            <li class="list-inline-item badge bg-secondary skill-item">Graphic Design</li>
            <li class="list-inline-item badge bg-info skill-item">Figma</li>
            <li class="list-inline-item badge bg-success skill-item">UX/UI Design</li>
          </ul>
          <h3 class="h5 mt-4 experience-title">Experience</h3>
          <p class="experience-description">
            With a background in both web development and design, I have had the privilege of working on diverse projects that bridge the gap between technical and creative solutions. My journey has led me to build responsive websites, intuitive user interfaces, and engaging graphic designs that aim to provide users with exceptional experiences across devices.
          </p>
          <p class="experience-description">
            As a Senior Web Developer and Designer at XYZ Solutions, I lead a multidisciplinary team of developers and designers to deliver projects that meet both functional and aesthetic standards. From wireframing to front-end development, I am committed to crafting clean, optimized, and user-centric digital solutions.
          </p>
          <h3 class="h5 mt-4 contact-title">Contact</h3>
          <p class="contact-description">
            If you’re interested in collaborating on a project, or if you simply want to connect, feel free to reach out via <a href="mailto:deep.sing@example.com">email</a>.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AboutMe',
  data() {
    return {
    }
  },
}
</script>

<style scoped>
.about-me-section {
  background-color: #BFA78A;
  position: relative;
  overflow: hidden;
}

.profile-image-container {
  width: 200px;
  height: 200px; 
  margin: 0 auto;
  position: relative;
  border-radius: 50%; 
  overflow: hidden; 
}

.profile-image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover; 
}

.profile-img {
  transform: scale(1);
  transition: transform 0.5s ease;
}

.profile-img:hover {
  transform: scale(1.1);
}



.about-me-description {
  font-family: 'Arial', sans-serif;
  color: #ffffff;
  font-size: 1.25rem;
  letter-spacing: 0.5px;
  line-height: 1.8;
  animation: fadeIn 1.5s ease-out;
  margin-bottom: 40px;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.skills-title {
  font-family: 'Roboto', sans-serif;
  color: #dfe2e6;
  font-size: 1.5rem;
  font-weight: 500;
  margin-top: 30px;
  animation: fadeUp 1.5s ease-in-out;
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.skills-list {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  gap: 10px;
  animation: slideIn 1.5s ease-out;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.skills-list .badge {
  font-size: 1.2rem;
  padding: 10px 20px;
  margin: 10px;
  cursor: pointer;
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.skills-list .badge:hover {
  background-color: #0044cc;
  transform: translateY(-5px) scale(1.1);
}

.experience-title, .contact-title {
  font-family: 'Roboto', sans-serif;
  color: #dfe2e6;
  font-size: 1.5rem;
  font-weight: 500;
  margin-top: 40px;
  animation: fadeIn 1.5s ease-out;
}

.experience-description, .contact-description {
  font-family: 'Arial', sans-serif;
  color: #ffffff;
  font-size: 1rem;
  line-height: 1.8;
  margin-bottom: 20px;
}

.experience-description {
  animation: fadeInLeft 2s ease-out;
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.contact-description {
  animation: fadeInRight 2s ease-out;
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@media (max-width: 767px) {
  .profile-image-container {
    width: 150px;
    height: 150px;
  }

  .about-me-title {
    font-size: 2rem;
  }

  .about-me-description {
    font-size: 1rem;
  }

  .skills-title, .experience-title, .contact-title {
    font-size: 1.25rem;
  }

  .skills-list .badge {
    font-size: 1rem;
    padding: 8px 16px;
  }
}

.about-me-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #6a11cb, #2575fc);
  animation: gradientAnimation 10s ease infinite;
  z-index: -1;
}

@keyframes gradientAnimation {
  0% {
    background-position: 0 0;
  }
  50% {
    background-position: 100% 100%;
  }
  100% {
    background-position: 0 0;
  }
}
</style>
