<script setup>
import { onMounted } from "vue";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { images } from "../assets/images";

gsap.registerPlugin(ScrollTrigger);

const stats = [
  { number: 25, suffix: "+", text: "Years Experience" },
  { number: 500, suffix: "+", text: "Projects Completed" },
  { number: 1000, suffix: "+", text: "Employees" },
  { number: 50, suffix: "+", text: "Awards Won" },
];

onMounted(() => {
  gsap.from(".stat-number", {
    scrollTrigger: {
      trigger: ".stats-section",
      start: "top center",
    },
    duration: 2,
    opacity: 0,
    y: 50,
    stagger: 0.2,
    ease: "power2.out",
  });
});
</script>

<template>
  <section id="about" class="about-section">
    <div class="container">
      <div class="about-grid">
        <div class="about-content">
          <h2 class="section-title">Who We Are</h2>
          <p>
            With over 25 years of experience, we've established ourselves as a
            leader in construction and civil engineering. Our commitment to
            quality, innovation, and sustainability has made us the trusted
            choice for projects of all scales.
          </p>
          <p>
            From residential buildings to industrial complexes, we bring
            expertise, dedication, and cutting-edge technology to every project
            we undertake.
          </p>
          <a href="#contact" class="btn">Learn More</a>
        </div>
        <div class="about-image">
          <img :src="images.about" alt="About Us" />
        </div>
      </div>

      <div class="stats-section">
        <div class="stats-grid">
          <div v-for="stat in stats" :key="stat.text" class="stat-item">
            <div class="stat-number">{{ stat.number }}{{ stat.suffix }}</div>
            <div class="stat-text">{{ stat.text }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 5rem 0;
}

.about-grid {
  display: grid;
  gap: 3rem;
  margin-bottom: 5rem;
}

.about-content h2 {
  margin-bottom: 1.5rem;
}

.about-content p {
  color: var(--text-light);
  margin-bottom: 1.5rem;
}

.about-image img {
  width: 100%;
  border-radius: 0.5rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.stats-section {
  margin-top: 5rem;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 2rem;
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: bold;
  color: var(--primary);
  margin-bottom: 0.5rem;
}

.stat-text {
  color: var(--text-light);
}

@media (min-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }

  .stats-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>
