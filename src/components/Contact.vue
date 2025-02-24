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

      <!-- <div class="contact-content">
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
      </div>-->
      <div class="contact_us">
        <div class="map-image">
          <img src="../assets/map-image.jpg"/>
          <div class="contact-address">
            <p>
              B 102 Dolphin Empress<br />
              Dr Bheem Rao Ambetkar Ward 27<br />
              Mova Raipur, Chattisgarh<br />
              492001, India
            </p>
          </div>
        </div>
        <div class="get-in-touch mt-3">
          <div class="single-touch">
            <a href="mailto:info@example.com" class="email">info@example.com</a>
          </div>
          <div class="single-touch">
            <a href="tel:+919831012345" class="phone">+91 9831 012 345</a>
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
.map-image {
    width: 100%;
    height: 425px;
    overflow: hidden;
    border-radius: 20px;
    box-shadow: 0 0 6px rgba(0,0,0,0.2);
    position: relative;
}
.contact-address {
    position: absolute;
    top: 30px;
    left: 30px;
    background: #fff;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 0 6px rgba(0,0,0,0.2);
}
.contact-address p {
    padding-left: 25px;
    background-image: url("data:image/svg+xml,%3C%3Fxml version='1.0' encoding='utf-8'%3F%3E%3C!-- Uploaded to: SVG Repo, www.svgrepo.com, Generator: SVG Repo Mixer Tools --%3E%3Csvg width='800px' height='800px' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M3.37892 10.2236L8 16L12.6211 10.2236C13.5137 9.10788 14 7.72154 14 6.29266V6C14 2.68629 11.3137 0 8 0C4.68629 0 2 2.68629 2 6V6.29266C2 7.72154 2.4863 9.10788 3.37892 10.2236ZM8 8C9.10457 8 10 7.10457 10 6C10 4.89543 9.10457 4 8 4C6.89543 4 6 4.89543 6 6C6 7.10457 6.89543 8 8 8Z' fill='%23f00'/%3E%3C/svg%3E");
    background-size: 25px;
    background-position: left -3px top;
    background-repeat: no-repeat;
}
.get-in-touch{
    margin-top: 25px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 15px;
}
.single-touch {
    background: #ffffff;
    padding: 25px 0;
    width: 50%;
    border-radius: 12px;
    box-shadow: 0 0 6px rgba(0,0,0,0.2);
}
.single-touch a {
    padding-left: 50px;
    font-size: 18px;
    font-weight: 500;
}
a.email{
  background-image: url("data:image/svg+xml,%3C%3Fxml version='1.0' encoding='utf-8'%3F%3E%3C!-- Uploaded to: SVG Repo, www.svgrepo.com, Generator: SVG Repo Mixer Tools --%3E%3Csvg width='800px' height='800px' viewBox='0 0 24 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M4 7.00005L10.2 11.65C11.2667 12.45 12.7333 12.45 13.8 11.65L20 7' stroke='%23333333' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'/%3E%3Crect x='3' y='5' width='18' height='14' rx='2' stroke='%23333333' stroke-width='2' stroke-linecap='round'/%3E%3C/svg%3E");
  background-size: 25px;
  background-repeat: no-repeat; 
  background-position: left 16px center;
}
.phone{
  background-image: url("data:image/svg+xml,%3C%3Fxml version='1.0' encoding='utf-8'%3F%3E%3C!-- Uploaded to: SVG Repo, www.svgrepo.com, Generator: SVG Repo Mixer Tools --%3E%3Csvg width='800px' height='800px' viewBox='0 0 24 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M3 5.5C3 14.0604 9.93959 21 18.5 21C18.8862 21 19.2691 20.9859 19.6483 20.9581C20.0834 20.9262 20.3009 20.9103 20.499 20.7963C20.663 20.7019 20.8185 20.5345 20.9007 20.364C21 20.1582 21 19.9181 21 19.438V16.6207C21 16.2169 21 16.015 20.9335 15.842C20.8749 15.6891 20.7795 15.553 20.6559 15.4456C20.516 15.324 20.3262 15.255 19.9468 15.117L16.74 13.9509C16.2985 13.7904 16.0777 13.7101 15.8683 13.7237C15.6836 13.7357 15.5059 13.7988 15.3549 13.9058C15.1837 14.0271 15.0629 14.2285 14.8212 14.6314L14 16C11.3501 14.7999 9.2019 12.6489 8 10L9.36863 9.17882C9.77145 8.93713 9.97286 8.81628 10.0942 8.64506C10.2012 8.49408 10.2643 8.31637 10.2763 8.1317C10.2899 7.92227 10.2096 7.70153 10.0491 7.26005L8.88299 4.05321C8.745 3.67376 8.67601 3.48403 8.55442 3.3441C8.44701 3.22049 8.31089 3.12515 8.15802 3.06645C7.98496 3 7.78308 3 7.37932 3H4.56201C4.08188 3 3.84181 3 3.63598 3.09925C3.4655 3.18146 3.29814 3.33701 3.2037 3.50103C3.08968 3.69907 3.07375 3.91662 3.04189 4.35173C3.01413 4.73086 3 5.11378 3 5.5Z' stroke='%23333333' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");
  background-size: 25px;
  background-repeat: no-repeat; 
  background-position: left 16px center;
}
@media (max-width: 768px) {
  .contact {
    padding: 4rem 1rem;
  }

  .section-title {
    font-size: 2rem;
  }
  .map-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .contact-address{
    left: 14px;
  }
  .get-in-touch{
    flex-direction: column;
  }
  .single-touch{
    width: 100%;
  }
}
</style>
