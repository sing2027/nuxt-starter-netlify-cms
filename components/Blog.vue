<template>
  <div class="blog-container">
    <h1 class="New-title-Animation text-center mb-4">Our Blog</h1>

    <div class="blog-posts-grid">
      <div
        v-for="(post, index) in posts"
        :key="post.id"
        class="blog-post"
        @mouseover="onHover(index)"
        @mouseleave="onLeave(index)"
      >
        <div class="post-header">
          <h2 class="post-title">{{ post.title }}</h2>
          <p class="post-date">{{ post.date }}</p>
        </div>

        <div class="post-content">
          <p class="post-text">{{ truncateText(post.content, 25) }}</p>
        </div>

        <div class="post-image">
          <img :src="post.image" :alt="post.title" />
        </div>
      </div>
    </div>

    <div v-if="showModal" class="modal-overlay" @click="closeModal">
      <div class="modal-content" @click.stop>
        <h2>Submit a Comment</h2>
        <textarea v-model="modalComment" placeholder="Write your comment..." rows="5"></textarea>
        <div class="modal-buttons">
          <button @click="submitComment" class="submit-comment-btn">Submit</button>
          <button @click="closeModal" class="cancel-comment-btn">Cancel</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newComment: '',
      modalComment: '',
      showModal: false,
      posts: [
        {
          id: 1,
          title: 'The Future of Web Development',
          date: 'October 1, 2024',
          content:
            'Web development is constantly evolving with new tools, libraries, and frameworks. In this post, we explore the future of web development and the latest trends...',
          image: '/img/TheFutureofWebDevelopment.jpg',
        },
        {
          id: 2,
          title: 'How to Build a Vue.js App',
          date: 'October 5, 2024',
          content:
            'Vue.js is a progressive JavaScript framework used for building user interfaces. This post covers how to set up a simple Vue.js application and explains its core concepts...',
          image: '/img/HowtoBuildaVuejsApp.jpg',
        },
        {
          id: 3,
          title: 'Understanding Static Websites',
          date: 'October 7, 2024',
          content:
            'In the world of web development, static websites are often overlooked in favor of more dynamic, data-driven sites. However, static websites remain a powerful and efficient solution for many use cases. A static website is one where each page is pre-rendered as an HTML file, meaning there is no server-side processing or database interaction to generate content. This makes static websites incredibly fast, reliable, and easy to deploy. In this blog post, we will explore the key benefits of static websites, such as improved performance, security, and cost-effectiveness, as well as a step-by-step guide on how to build a basic static website using modern tools like HTML, CSS, and static site generators like Jekyll or Hugo. Whether you’re creating a personal portfolio, a simple blog, or a landing page, static websites offer a streamlined approach to building fast and scalable web projects.',
          image: '/img/staticsites.jpg',
        },
      ],
    };
  },
  methods: {
    truncateText(text, wordLimit) {
      const words = text.split(' ');
      if (words.length <= wordLimit) {
        return text;
      }
      return words.slice(0, wordLimit).join(' ') + '...';
    },
    openModal() {
      this.showModal = true;
    },
    closeModal() {
      this.showModal = false;
    },
    submitComment() {
      alert('Comment Submitted: ' + this.modalComment);
      this.closeModal();
    },
    onHover(index) {
      this.$set(this.posts[index], 'hovered', true);
    },
    onLeave(index) {
      this.$set(this.posts[index], 'hovered', false);
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
}

.blog-container {
  max-width: 1440px;
  margin: 0 auto;
  padding: 40px;
  background-color: #bfa78a;
}

.blog-title-Animation {
  text-align: center;
  font-size: 3.5rem;
  color: #333;
  font-weight: 700;
  letter-spacing: 2px;
  margin-bottom: 50px;
  text-transform: uppercase;
  animation: fadeIn 1s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.blog-posts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 30px;
  margin-bottom: 40px;
}

.blog-post {
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.blog-post:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
}

.post-header {
  padding: 20px;
  background: #00796b;
  color: #fff;
  border-bottom: 2px solid #004d40;
}

.post-title {
  font-size: 2.2rem;
  font-weight: 600;
}

.post-date {
  font-size: 1rem;
  margin-top: 5px;
  opacity: 0.7;
}

.post-content {
  padding: 20px;
}

.post-text {
  font-size: 1.1rem;
  color: #555;
  line-height: 1.7;
  margin-bottom: 20px;
}

.post-image img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.blog-post:hover .post-image img {
  transform: scale(1.05);
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  background: white;
  padding: 30px;
  border-radius: 10px;
  width: 400px;
}

.modal-buttons button {
  margin-top: 20px;
  background-color: #00796b;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.modal-buttons button:hover {
  background-color: #004d40;
}
</style>
