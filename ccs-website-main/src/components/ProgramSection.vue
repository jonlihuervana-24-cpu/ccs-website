<template>
  <section class="programs" id="program">
    <div class="container">
      <div class="section-header">
        <p class="subheading">Academic Programs</p>
        <h2>What We Offer</h2>
        <div class="gold-line"></div>
      </div>
      <div class="program-grid">
        <div class="program-card">
          <div class="card-icon">
            <img :src="bscsImg" alt="BS Computer Science" />
          </div>
          <span class="program-tag">BSCS</span>
          <h3>Bachelor of Science in Computer Science</h3>
          <p>Designed for in-depth study of computing — focused on software, hardware, algorithms, and the theoretical foundations of computation.</p>
        </div>

        <div class="program-card">
          <div class="card-icon">
            <img :src="bsitImg" alt="BS Information Technology" />
          </div>
          <span class="program-tag">BSIT</span>
          <h3>Bachelor of Science in Information Technology</h3>
          <p>Bridges the gap between computer science and information systems — practical skills in infrastructure, applications, and technology management.</p>
        </div>

        <div class="program-card">
          <div class="card-icon">
            <img :src="dmiaImg" alt="BS Digital Media & Interactive Arts" />
          </div>
          <span class="program-tag">BSDMIA</span>
          <h3>Bachelor of Science in Digital Media & Interactive Arts</h3>
          <p>Where creativity meets technology — animation, game design, digital publishing, and interactive media production.</p>
        </div>

        <div class="program-card">
          <div class="card-icon">
            <img :src="blisImg" alt="BLIS" />
          </div>
          <span class="program-tag">BLIS</span>
          <h3>Bachelor of Library & Information Science</h3>
          <p>Four-year program building expertise in information organization, library systems, archiving, and knowledge management.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import bscsImg from '@/assets/images/bscs.png'
import bsitImg from '@/assets/images/bsit.png'
import dmiaImg from '@/assets/images/dmia.png'
import blisImg from '@/assets/images/blis.png'
</script>

<style scoped>
.programs {
  padding: 6rem 1.5rem;
  background: #f8fafc;
  scroll-margin-top: 80px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
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
  margin: 0 auto;
  border-radius: 2px;
}

.program-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
  width: 100%;
}

.program-card {
  background: #ffffff;
  border: 1px solid #f1f5f9;
  border-top: 4px solid #b8860b;
  border-radius: 16px;
  padding: 2rem 1.5rem;
  text-align: center;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.02), 0 2px 4px -2px rgba(0, 0, 0, 0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100%;
}

.program-card:hover {
  transform: translateY(-4px);
  border-color: #e2e8f0;
  border-top-color: #d4af37;
  box-shadow: 0 12px 20px -5px rgba(0, 0, 0, 0.06), 0 4px 6px -2px rgba(0, 0, 0, 0.03);
}

.card-icon {
  width: 85px;
  height: 85px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f8fafc;
  border-radius: 12px;
  padding: 0.75rem;
  border: 1px solid #f1f5f9;
  margin-bottom: 1.25rem;
}

.card-icon img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.04));
  transition: transform 0.3s ease;
}

.program-card:hover .card-icon img {
  transform: scale(1.05);
}

.program-tag {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 800;
  letter-spacing: 1px;
  color: #b8860b;
  background: #fefce8;
  border: 1px solid #fef9c3;
  padding: 0.2rem 0.6rem;
  border-radius: 6px;
  margin-bottom: 0.75rem;
}

.program-card h3 {
  color: #1e293b;
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 0.75rem;
  line-height: 1.35;
}

.program-card p {
  color: #64748b;
  font-size: 0.9rem;
  line-height: 1.6;
  margin: 0;
}

@media (max-width: 1024px) {
  .program-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .programs {
    padding: 4rem 1rem;
  }

  .program-grid {
    grid-template-columns: 1fr;
    gap: 1.25rem;
  }

  .program-card {
    padding: 1.75rem 1.25rem;
  }
}
</style>