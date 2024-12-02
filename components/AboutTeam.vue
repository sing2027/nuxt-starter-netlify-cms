<template>
    <section class="about-team ">
      <h2 class="title-Animation">Meet Our Team</h2>
      
      <div class="team-cards">
        <div
          class="team-card "
          v-for="(member, index) in teamMembers"
          :key="index"
          @click="toggleModal(member)"
        >
          <img :src="member.photo" :alt="member.name" class="team-photo" />
          <div class="overlay">
            <div class="overlay-content">
              <h3>{{ member.name }}</h3>
              <p>{{ member.role }}</p>
            </div>
          </div>
        </div>
      </div>
  
      <div v-if="showModal" class="modal" @click="closeModal">
        <div class="modal-content" @click.stop>
          <h2>{{ modalData.name }}</h2>
          <p>{{ modalData.description }}</p>
          <button @click="closeModal">Close</button>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
   
    data() {
      return {
        showModal: false,
        modalData: {},
        teamMembers: [
          {
            name: "John Doe",
            role: "Front-end Developer",
            photo: "/img/men11.jpg",
            description: "John is passionate about building beautiful and user-friendly interfaces.",
          },
          {
            name: "Jane Smith",
            role: "Back-end Developer",
            photo: "/img/Teammember2.jpg",
            description: "Jane specializes in building scalable and efficient server-side applications.",
          },
          {
            name: "Mike Johnson",
            role: "UI/UX Designer",
            photo: "/img/Teammember3.jpg",
            description: "Mike is dedicated to creating seamless and intuitive user experiences.",
          },
        ],
      };
    },
    methods: {
      toggleModal(member) {
        this.showModal = true;
        this.modalData = {
          name: member.name,
          description: member.description,
        };
      },
      closeModal() {
        this.showModal = false;
        this.modalData = {};
      },
    },
  };
  </script>
  
  <style scoped>
  .about-team {
    padding: 50px 20px;
    background: #BFA78A;
    text-align: center;
  }
  
  .about-team h2 {
    font-size: 2.5rem;
    margin-bottom: 40px;
    color: #67272B;
  }
  
  .team-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
  }
  
  .team-card {
    position: relative;
    width: 250px;
    height: 350px;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .team-photo {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }
  
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    transition: opacity 0.3s ease;
  }
  
  .overlay-content {
    text-align: center;
    color: white;
    transform: translateY(50px);
    transition: transform 0.3s ease;
  }
  
  .overlay-content h3 {
    font-size: 1.5rem;
    margin: 0;
  }
  
  .overlay-content p {
    font-size: 1rem;
    margin-top: 5px;
  }
  
  .team-card:hover .overlay {
    opacity: 1;
  }
  
  .team-card:hover .overlay-content {
    transform: translateY(0);
  }
  
  .team-card:hover {
    transform: scale(1.05);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
  }
  
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }
  
  .modal-content {
    background: white;
    padding: 30px;
    border-radius: 10px;
    width: 80%;
    max-width: 600px;
    text-align: center;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
  }
  
  button {
    padding: 10px 20px;
    background-color: #f7b731;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 20px;
  }
  
  button:hover {
    background-color: #f39c12;
  }
  </style>
  