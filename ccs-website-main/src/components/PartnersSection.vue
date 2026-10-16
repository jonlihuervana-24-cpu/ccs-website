<template>
  <section class="partners" id="partners">
    <div class="container">
      <div class="section-header">
        <p class="subheading">Industry Connections</p>
        <h2>Partners & Memberships</h2>
        <div class="gold-line"></div>
      </div>
      <p class="intro">Leading organizations supporting our students' growth and career development</p>
      <div class="partners-grid">
        <div class="partner-card" v-for="(p, i) in partners" :key="i">
          <div class="logo-wrapper">
            <img :src="getImg(p.file)" :alt="p.name" />
          </div>
          <h4>{{ p.name }}</h4>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const getImg = (filename) => new URL(`/src/assets/images/${filename}`, import.meta.url).href

const partners = ref([
  { name: 'Oracle', file: 'oracle.png' },
  { name: 'Cisco', file: 'cisco.png' },
  { name: 'Acer', file: 'acer.jpg' },
  { name: 'Huawei', file: 'huawei.jpg' }
])
</script>

<style scoped>
.partners {
  padding: 6rem 1.5rem;
  background: #ffffff;
  scroll-margin-top: 80px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
  width: 100%;
}

.section-header {
  margin-bottom: 1.5rem;
}

.subheading {
  color: #b8860b;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  margin: 0 0 0.5rem;
  font-size: 0.875rem;
}

h2 {
  color: #1e293b;
  font-size: clamp(2rem, 4vw, 2.75rem);
  font-weight: 800;
  letter-spacing: -0.025em;
  margin: 0 0 1rem;
}

.gold-line {
  width: 60px;
  height: 3px;
  background: #b8860b;
  margin: 0 auto 1.5rem;
  border-radius: 2px;
}

.intro {
  color: #64748b;
  font-size: 0.975rem;
  max-width: 600px;
  margin: 0 auto 3.5rem;
  line-height: 1.6;
}

.partners-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
  width: 100%;
}

.partner-card {
  background: #ffffff;
  border: 1px solid #f1f5f9;
  border-radius: 16px;
  padding: 2.5rem 1.5rem;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.02), 0 2px 4px -2px rgba(0, 0, 0, 0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.partner-card:hover {
  transform: translateY(-4px);
  border-color: #e2e8f0;
  box-shadow: 0 12px 20px -5px rgba(0, 0, 0, 0.06), 0 4px 6px -2px rgba(0, 0, 0, 0.03);
}

.logo-wrapper {
  width: 100%;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.25rem;
}

.partner-card img {
  max-width: 110px;
  max-height: 70px;
  width: auto;
  height: auto;
  object-fit: contain;
  filter: grayscale(100%) opacity(0.75);
  transition: all 0.3s ease;
}

.partner-card:hover img {
  filter: grayscale(0%) opacity(1);
  transform: scale(1.05);
}

.partner-card h4 {
  color: #1e293b;
  font-size: 0.975rem;
  font-weight: 700;
  margin: 0;
  letter-spacing: -0.01em;
}

@media (max-width: 900px) {
  .partners {
    padding: 4rem 1rem;
  }

  .intro {
    margin-bottom: 2.5rem;
  }

  .partners-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .partner-card {
    padding: 2rem 1rem;
  }
}

@media (max-width: 480px) {
  .partners-grid {
    grid-template-columns: 1fr;
  }
}
</style>