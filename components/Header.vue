<template>
  <div class="relative bg-header">
    <div class="container">
      <div class="d-flex justify-content-between align-items-center py-4">
        <div>
          <nuxt-link to="/" class="logo-link">
            Portfolio
          </nuxt-link>
        </div>
<div class="d-block d-md-none">
  <button
    type="button"
    class="btn btn-link p-2"
    @click="toggleMenu"
    style="border: none; background: none;"
  >
    <img
      src="/img/icon-menu.svg" 
      alt="Menu"
      class="w-6 h-6"
      style="display:block; filter: invert(1) brightness(100%);"
    />
  </button>
</div>



        <div v-show="!menuOpen" class="d-none d-md-flex flex-grow-1 justify-content-end">
          <nav class="d-flex space-x-10">
            <nuxt-link to="/" class="nav-link"> Home </nuxt-link>
            <nuxt-link to="/about" class="nav-link"> About </nuxt-link>
            <nuxt-link to="/projects" class="nav-link"> Projects </nuxt-link>
            <nuxt-link to="/blog" class="nav-link"> Blog </nuxt-link>
            <nuxt-link to="/contact" class="nav-link"> Contact </nuxt-link>
          </nav>
        </div>
      </div>

      <div v-show="menuOpen" class="absolute inset-x-0 top-0 z-50 p-2 transition transform md-hidden">
        <div class="rounded-lg shadow-lg">
          <div class="bg-custom divide-y-2 rounded-lg shadow-xs divide-gray-50">
            <div class="px-5 pt-2 pb-6 space-y-6">
              <div class="d-flex justify-content-end">
                <div>
<button
  type="button"
  class="btn btn-link"
  @click="toggleMenu"
>
 
  <img
      src="/img/icon-close-menu.svg" 
      alt="Menu"
      class="w-6 h-6 bg-danger p-2 rounded-circle"
      style="display:block; color: red !important;;"
    />
    <path
      stroke-linecap="round"
      stroke-linejoin="round"
      stroke-width="2"
      d="M6 18L18 6M6 6l12 12"
    />
</button>

                </div>
              </div>
            </div>
            <div class="px-5 py-6">
              <div class="d-flex flex-column">
                <nuxt-link to="/" class="dropdown-item" @click.native="toggleMenu">
                  Home
                </nuxt-link>
                <nuxt-link to="/about" class="dropdown-item" @click.native="toggleMenu">
                  About
                </nuxt-link>
                <nuxt-link to="/projects" class="dropdown-item" @click.native="toggleMenu">
                  Projects
                </nuxt-link>
                <nuxt-link to="/blog" class="dropdown-item" @click.native="toggleMenu">
                  Blog
                </nuxt-link>
                <nuxt-link to="/contact" class="dropdown-item" @click.native="toggleMenu">
                  Contact
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen
    },
  },
}
</script>

<style scoped>
.logo-link {
  font-family: 'Roboto', sans-serif; 
  font-size: 2.5rem; 
  font-weight: 700; 
  color: #e7ecec;
  text-transform: uppercase; 
  letter-spacing: 5px; 
  text-decoration: none; 
  position: relative; 
  display: inline-block; 
  transition: color 0.3s ease, transform 0.3s ease; 
}

.logo-link::before {
  content: ''; 
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, rgba(0, 0, 0, 0.1) 25%, transparent 50%, rgba(0, 0, 0, 0.1) 75%);
  filter: blur(5px);
  z-index: -1;
  transition: opacity 0.3s ease;
}
.bg-custom {
  background-color: transparent;
  box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.5); 
}


.logo-link:hover {
  color: #00796b; 
  transform: scale(1.1); 
}

.logo-link:hover::before {
  opacity: 0.4; 
}

.logo-link span {
  background: linear-gradient(135deg, #00796b, #004d40);
  -webkit-background-clip: text;
  color: transparent;
}

@media (max-width: 767px) {
  .logo-link {
    font-size: 2rem; 
    letter-spacing: 3px; 
  }
}

.nav-link {
  font-size: 1rem;
  font-weight: 500;
  color: #ffffff; 
  text-transform: none;
  padding: 0.5rem 1rem;
  transition: color 0.2s ease;
}
.bg-header {
  background-color: #ffffff; 
}

.nav-link:hover {
  color: #c0a8a8; 
}

.dropdown-item {
  font-size: 1rem;
  font-weight: 500;
  color: #ffffff;
  padding: 0.5rem 1rem;
  transition: color 0.2s ease;
}

.dropdown-item:hover {
  color: #1f2937;
}
</style>
