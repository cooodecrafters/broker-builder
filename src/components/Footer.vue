<script setup>
const sectors = {
  Projects: ["Buildings", "Civil", "Industrial"],
  "Who We Are": ["About Us", "Our Leadership", "CEO Message", "Our History"],
  Company: ["Safety", "Mission", "Vision", "Careers"],
  Contact: ["Contact Us", "Locations", "Support"],
};
</script>

<template>
  <footer class="site-footer">
    <div class="container">
      <div class="footer-grid">
        <div
          v-for="(items, section) in sectors"
          :key="section"
          class="footer-section"
        >
          <h3>{{ section }}</h3>
          <ul>
            <li v-for="item in items" :key="item">
              <a href="#">{{ item }}</a>
            </li>
          </ul>
        </div>
      </div>

      <div class="footer-bottom">
        <p>
          &copy; {{ new Date().getFullYear() }} Builder Company. All rights
          reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background: var(--bg-dark);
  color: var(--white);
  padding: 4rem 0 2rem;
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.footer-section h3 {
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: 1.5rem;
}

.footer-section ul {
  list-style: none;
}

.footer-section ul li {
  margin-bottom: 0.75rem;
}

.footer-section a {
  color: var(--text-light);
  text-decoration: none;
  transition: color 0.3s;
}

.footer-section a:hover {
  color: var(--white);
}

.footer-bottom {
  text-align: center;
  padding-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  color: var(--text-light);
}
</style>
