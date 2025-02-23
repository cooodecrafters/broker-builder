<script setup>
import { onMounted } from "vue";
import gsap from "gsap";
import { images } from "../assets/images";

onMounted(() => {
  gsap.from(".hero-text", {
    duration: 1,
    y: 30,
    opacity: 0,
    stagger: 0.2,
    ease: "power2.out",
  });
});
</script>

<template>
  <section class="hero" id="home">
    <div class="hero-bg">
      <img :src="images.hero" alt="Hero Background" />
    </div>
    <div class="container">
      <div class="hero-content">
        <h1 class="hero-title hero-text">Building Tomorrow's World Today</h1>
        <p class="hero-subtitle hero-text">
          Excellence in Construction, Civil Engineering, and Industrial Projects
        </p>
        <a href="#projects" class="hero-btn hero-text">Explore Our Projects</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  height: 100vh;
  display: flex;
  align-items: center;
  color: var(--white);
}

.hero-bg {
  position: absolute;
  inset: 0;
  z-index: -1;
}

.hero-bg::after {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.5); /* Simplified overlay */
}

.hero-bg img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-content {
  max-width: 800px;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1.5rem;
  background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.hero-subtitle {
  font-size: clamp(1.1rem, 2vw, 1.5rem);
  margin-bottom: 2.5rem;
  background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  max-width: 600px;
  line-height: 1.6;
}

.hero-btn {
  display: inline-block;
  padding: 1rem 2.5rem;
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--white);
  background: #000000;
  border-radius: 50px;
  text-decoration: none;
  transition: all 0.3s ease;
}

.hero-btn:hover {
  transform: translateY(-2px);
  background: #000000;
}

@media (max-width: 768px) {
  .hero-content {
    text-align: center;
    padding: 0 1rem;
  }

  .hero-btn {
    padding: 0.875rem 2rem;
    font-size: 1rem;
  }
}
</style>
