<template>
    <div class="projects-container">
      <h1 class="New-title-Animation text-center mb-4">Our Projects</h1>
  
      <div class="projects-grid">
        <div
          v-for="(project, index) in projects"
          :key="project.id"
          class="project-card"
          @mouseover="onHover(index)"
          @mouseleave="onLeave(index)"
        >
          <div class="card-header">
            <h2 class="card-title">{{ project.title }}</h2>
            <p class="card-date">{{ project.date }}</p>
          </div>
  
          <div class="card-content">
            <p class="card-text">
              {{ project.isReadMore ? project.description : project.description.substring(0, 150) + '...' }}
            </p>
          </div>
  
          <div class="card-image">
            <img :src="project.image" :alt="project.title" />
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        projects: [
          {
            id: 1,
            title: 'E-commerce Website',
            date: 'July 25, 2024',
            description:
              'This project involves creating a fully functional e-commerce website with features like product listing, payment integration, and user profiles.',
            isReadMore: false,
            image: '/img/EcommerceWebsite.jpg',
          },
          {
            id: 2,
            title: 'Mobile App Development',
            date: 'August 10, 2024',
            description:
              'This project focuses on building a cross-platform mobile app with Vue.js and Flutter, designed to enhance user engagement and performance.',
            isReadMore: false,
            image: '/img/MobileAppDevelopment.jpg',
          },
          {
            id: 3,
            title: 'Web Application for HR',
            date: 'September 15, 2024',
            description:
              'A web application that automates HR tasks such as payroll, employee records, and performance tracking.',
            isReadMore: false,
            image: '/img/WebApplicationforHR.jpg',
          },
        ],
      };
    },
    methods: {
      toggleReadMore(index) {
        this.projects[index].isReadMore = !this.projects[index].isReadMore;
      },
      onHover(index) {
        this.$set(this.projects[index], 'hovered', true);
      },
      onLeave(index) {
        this.$set(this.projects[index], 'hovered', false);
      },
    },
  };
  </script>
  
  <style scoped>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
    transition: all 0.3s ease;
  }
  
  .projects-container {
    max-width: 1440px;
    margin: 0 auto;
    padding: 40px;
    background-color: #bfa78a;
  }
  
  .title {
    text-align: center;
    font-size: 3rem;
    color: #333;
    font-weight: 700;
    letter-spacing: 1px;
    margin-bottom: 50px;
    text-transform: uppercase;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
  }
  
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 30px;
    margin-bottom: 40px;
  }
  
  @media (min-width: 768px) {
    .projects-grid {
      grid-template-columns: 1fr 1fr;
    }
  }
  
  @media (min-width: 1024px) {
    .projects-grid {
      grid-template-columns: 1fr 1fr 1fr;
    }
  }
  
  .project-card {
    display: flex;
    flex-direction: column;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transform: translateY(10px);
    animation: fadeInUp 0.6s ease-out forwards;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    height: 100%;
  }
  
  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
  }
  
  .card-header {
    padding: 20px;
    background: #00796b;
    color: #fff;
    border-bottom: 2px solid #004d40;
  }
  
  .card-title {
    font-size: 2.5rem;
    font-weight: 600;
    transition: transform 0.3s ease;
  }
  
  .card-title:hover {
    transform: scale(1.05);
  }
  
  .card-date {
    font-size: 1.1rem;
    margin-top: 5px;
    opacity: 0.8;
  }
  
  .card-content {
    flex-grow: 1;
    padding: 20px;
  }
  
  .card-text {
    font-size: 1.1rem;
    color: #555;
    line-height: 1.7;
    margin-bottom: 20px;
  }
  
.card-image {
  flex-shrink: 0;
  width: 100%;
  height: 250px; 
  overflow: hidden; 
}

.card-image img {
  width: 100%;
  height: 100%; 
  object-fit: cover; 
  transition: transform 0.5s ease;
}

.project-card:hover .card-image img {
  transform: scale(1.05);
}

  
  @keyframes fadeInUp {
    0% {
      opacity: 0;
      transform: translateY(10px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
  </style>
  