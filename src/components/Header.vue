<script setup>
import { ref } from "vue";
import { images } from "../assets/images";

const isMenuOpen = ref(false);
const props = defineProps(["activeSection"]);
const emit = defineEmits(["setActive"]);

const navigation = [
  { name: "Home", href: "#home" },
  { name: "Projects", href: "#projects" },
  { name: "About", href: "#about" },
  { name: "Contact", href: "#contact" },
];

const scrollToSection = (sectionId) => {
  const element = document.querySelector(sectionId);
  element?.scrollIntoView({ behavior: "smooth" });
  emit("setActive", sectionId.replace("#", ""));
  isMenuOpen.value = false;
};
</script>

<template>
  <header class="site-header">
    <nav class="nav-container">
      <div class="nav-wrapper">
        <div class="logo">
          <img :src="images.logo" alt="Builder Logo" />
        </div>

        <!-- Desktop Menu -->
        <div class="desktop-menu">
          <a
            v-for="item in navigation"
            :key="item.name"
            :href="item.href"
            @click.prevent="scrollToSection(item.href)"
            :class="[
              'nav-link',
              { active: props.activeSection === item.href.replace('#', '') },
            ]"
          >
            {{ item.name }}
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <button @click="isMenuOpen = !isMenuOpen" class="mobile-toggle">
          <svg
            class="menu-icon"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              v-if="!isMenuOpen"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path
              v-else
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div v-show="isMenuOpen" class="mobile-menu">
        <a
          v-for="item in navigation"
          :key="item.name"
          :href="item.href"
          @click.prevent="scrollToSection(item.href)"
          :class="[
            'mobile-link',
            { active: props.activeSection === item.href.replace('#', '') },
          ]"
        >
          {{ item.name }}
        </a>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.site-header {
  position: fixed;
  width: 100%;
  background: var(--white);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  z-index: 50;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem;
}

.nav-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo img {
  height: 48px;
}

.desktop-menu {
  display: none;
}

.nav-link {
  padding: 0.5rem 1rem;
  color: var(--text-dark);
  text-decoration: none;
  transition: color 0.3s;
}

.nav-link:hover,
.nav-link.active {
  color: var(--primary);
}

.mobile-toggle {
  display: block;
  padding: 0.5rem;
  background: none;
  border: none;
  cursor: pointer;
}

.menu-icon {
  width: 24px;
  height: 24px;
  color: var(--text-dark);
}

.mobile-menu {
  padding: 1rem 0;
  background: var(--white);
}

.mobile-link {
  display: block;
  padding: 0.75rem 1rem;
  color: var(--text-dark);
  text-decoration: none;
  transition: all 0.3s;
}

.mobile-link.active {
  background: var(--primary);
  color: var(--white);
}

@media (min-width: 768px) {
  .desktop-menu {
    display: flex;
    gap: 2rem;
  }

  .mobile-toggle {
    display: none;
  }

  .mobile-menu {
    display: none;
  }
}
</style>
