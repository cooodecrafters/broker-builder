<script setup>
import { computed, ref } from "vue";
import { images } from "../assets/images";

const categories = ["All", "Buildings", "Civil", "Industrial"];
const activeCategory = ref("All");

const projects = [
  {
    id: 1,
    title: "Modern Office Complex",
    category: "Buildings",
    image: images.projects.office,
    description: "State-of-the-art office building with sustainable features",
  },
  {
    id: 2,
    title: "Highway Bridge",
    category: "Civil",
    image: images.projects.bridge,
    description: "Major infrastructure project connecting communities",
  },
  {
    id: 3,
    title: "Steel Manufacturing Plant",
    category: "Industrial",
    image: images.projects.plant,
    description: "Large-scale industrial facility with cutting-edge technology",
  },
  // Add more projects as needed
];

const filteredProjects = computed(() => {
  return activeCategory.value === "All"
    ? projects
    : projects.filter((project) => project.category === activeCategory.value);
});
</script>

<template>
  <section class="projects" id="projects">
    <div class="container">
      <h2 class="section-title">Our Projects</h2>

      <div class="category-filters">
        <button
          v-for="category in categories"
          :key="category"
          @click="activeCategory = category"
          :class="['category-btn', { active: activeCategory === category }]"
        >
          {{ category }}
        </button>
      </div>

      <div class="projects-grid">
        <div
          v-for="project in filteredProjects"
          :key="project.id"
          class="project-card"
        >
          <img :src="project.image" :alt="project.title" />
          <div class="project-info">
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.project-card {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transform: translateY(0);
  transition: transform 0.3s;
}

.project-card:hover {
  transform: translateY(-8px);
}

.project-card img {
  width: 100%;
  height: 300px;
  object-fit: cover;
}

.project-info {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 1.5rem;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
  opacity: 0;
  transition: opacity 0.3s;
}

.project-card:hover .project-info {
  opacity: 1;
}

.project-info h3 {
  color: var(--white);
  margin-bottom: 0.5rem;
}

.project-info p {
  color: var(--white);
  font-size: 0.9rem;
}
</style>
