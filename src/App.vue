<script setup>
import { ref, onMounted } from "vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Hero from "./components/Hero.vue";
import Projects from "./components/Projects.vue";
import About from "./components/About.vue";
import Contact from "./components/Contact.vue";

const activeSection = ref("home");

const setActiveSection = (section) => {
  activeSection.value = section;
};

onMounted(() => {
  // Intersection Observer for scroll spy
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          setActiveSection(entry.target.id);
        }
      });
    },
    { threshold: 0.5 }
  );

  document.querySelectorAll("section").forEach((section) => {
    observer.observe(section);
  });
});
</script>

<template>
  <div class="app-wrapper">
    <Header :activeSection="activeSection" @setActive="setActiveSection" />

    <main class="main-content">
      <Hero />
      <Projects />
      <About />
      <Contact />
    </main>

    <Footer />
  </div>
</template>

<style>
:root {
  --header-height: 80px;
  --max-width: 1200px;
  --container-padding: 1rem;
}

.app-wrapper {
  min-height: 100vh;
  background: var(--bg-light);
  overflow-x: hidden;
}

.container {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--container-padding);
  width: 100%;
}

.main-content {
  padding-top: var(--header-height);
  position: relative;
}

section {
  padding: 5rem 0;
  position: relative;
}

/* Responsive typography */
h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
h2 {
  font-size: clamp(1.8rem, 4vw, 3rem);
}
h3 {
  font-size: clamp(1.5rem, 3vw, 2rem);
}

/* Global animations */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.slide-up-enter-active,
.slide-up-leave-active {
  transition: transform 0.5s ease-out, opacity 0.5s ease-out;
}

.slide-up-enter-from,
.slide-up-leave-to {
  transform: translateY(30px);
  opacity: 0;
}

/* Global utility classes */
.text-gradient {
  background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.section-padding {
  padding: clamp(3rem, 8vw, 6rem) 0;
}

/* Global section title style */
.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  font-weight: 700;
}

@media (max-width: 768px) {
  :root {
    --container-padding: 1.5rem;
  }

  section {
    padding: 3rem 0;
  }
}
</style>
