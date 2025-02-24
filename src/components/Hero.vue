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
      <div class="scroll-down-bg">
        <img src="../assets/scroll-down.gif"/>
      </div>
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
  /* background: linear-gradient(45deg, rgba(255,0,0,1) 0%,rgba(0,0,255,1) 100%); */
  background: url(../assets/hero.jpg) no-repeat center center / cover;
}

.hero-bg {
  position: absolute;
  inset: 0;
}

.hero-bg::after {
    content: "";
    position: absolute;
    height: 100%;
    width: 65%;
    left: 0;
    top: 0;
    background: linear-gradient(to right, rgba(255,0,0,1) 0%,rgba(0,0,255,1) 57%,rgba(136,136,255,0.3) 80%,rgba(255,255,255,0) 100%); 
    opacity: 0.5
}

.hero-bg img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-content {
  max-width: 800px;
    z-index: 12;
    position: relative;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1.5rem;
  /* background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text; */
  color: #ffffff;
}

.hero-subtitle {
  font-size: clamp(1.1rem, 2vw, 1.5rem);
  margin-bottom: 2.5rem;
  /* background: linear-gradient(45deg, #ff0000, #0000ff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent; */
  color: #ffffff;
  max-width: 600px;
  line-height: 1.6;
}

.hero-btn {
  display: inline-block;
  padding: 1rem 2.5rem;
  font-size: 1.1rem;
  font-weight: 600;
  color: #000000;
  background: #ffffff;
  border-radius: 50px;
  text-decoration: none;
  transition: all 0.3s ease;
}

.hero-btn:hover {
  transform: translateY(-2px);
  background: #000000;
  color: #ffffff;
}

.scroll-down-bg {
    width: 50px;
    position: absolute;
    left: 70px;
    bottom: 106px;
    z-index: 2;
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
  .hero-bg[data-v-edb47f11]::after {
    width: 100%;
  }
}
</style>
