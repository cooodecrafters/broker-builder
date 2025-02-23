<script setup>
import { onMounted } from "vue";
import gsap from "gsap";

onMounted(() => {
  gsap.from(".contact-item", {
    duration: 0.8,
    y: 20,
    opacity: 0,
    stagger: 0.2,
    ease: "power2.out",
  });
});
</script>

<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title contact-item">Contact Us</h2>
      <div class="contact-content">
        <div class="contact-info contact-item">
          <h3>Our Address</h3>
          <p>
            B 102 Dolphin Empress<br />
            Dr Bheem Rao Ambetkar Ward 27<br />
            Mova Raipur, Chattisgarh<br />
            492001, India
          </p>
        </div>
        <div class="contact-details contact-item">
          <h3>Get in Touch</h3>
          <div class="contact-links">
            <a href="mailto:info@example.com" class="contact-link">
              <i class="fas fa-envelope"></i> Email Us
            </a>
            <a href="tel:+911234567890" class="contact-link">
              <i class="fas fa-phone"></i> Call Us
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 6rem 0;
  background: var(--bg-light);
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.contact-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.contact-info,
.contact-details {
  padding: 2rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.contact-info h3,
.contact-details h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: var(--primary);
}

.contact-info p {
  line-height: 1.8;
  color: #666;
}

.contact-links {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: var(--primary);
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-link:hover {
  color: var(--primary-dark);
}

@media (max-width: 768px) {
  .contact {
    padding: 4rem 1rem;
  }

  .section-title {
    font-size: 2rem;
  }
}
</style>
