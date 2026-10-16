<template>
  <section class="hero" id="hero">
    <div class="container">
      <div class="hero-content">
        <img :src="logoImg" alt="CCS Logo" class="hero-logo" />
        <h1>College of Computer Studies</h1>
        <p class="motto">Building bridges between gaps — different people, one goal</p>
        <div class="values">
          <span>REMEMBER</span>
          <span>CONNECT</span>
          <span>ENGAGE</span>
          <span>BUILD</span>
          <span>SHARE</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import logoImg from '@/assets/images/ccs-logo.png'
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 1.5rem;
  background: radial-gradient(circle at top, #eaebeb 0%, #ffffff 100%);
  text-align: center;
  scroll-margin-top: 100px;
}

.container {
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
}

.hero-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 900px;
  margin: 0 auto;
}

.hero-logo {
  width: 180px;
  height: 180px;
  object-fit: contain;
  margin-bottom: 2rem;
  filter: drop-shadow(0 10px 15px rgba(0, 0, 0, 0.08));
  transition: transform 0.3s ease;
}

.hero-logo:hover {
  transform: translateY(-4px);
}

.hero h1 {
  color: #1e293b;
  font-size: clamp(2.2rem, 5vw, 3.75rem);
  font-weight: 800;
  letter-spacing: -0.025em;
  margin-bottom: 1rem;
  line-height: 1.15;
}

.motto {
  color: #64748b;
  font-size: clamp(1rem, 2vw, 1.25rem);
  font-weight: 400;
  max-width: 600px;
  margin-bottom: 3.5rem;
  line-height: 1.6;
}

.values {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.75rem;
  flex-wrap: wrap;
}

.values span {
  color: #334155;
  font-weight: 700;
  font-size: 0.875rem;
  padding: 0.6rem 1.2rem;
  background: #ffffff;
  border: 1px solid #e2e8f0;
  border-bottom: 3px solid #b8860b;
  border-radius: 8px;
  letter-spacing: 1.5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02);
  transition: all 0.2s ease;
}

.values span:hover {
  border-bottom-color: #d4af37;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.06);
}

@media (max-width: 900px) {
  .hero {
    padding: 3rem 1rem;
  }
  
  .hero-logo {
    width: 140px;
    height: 140px;
    margin-bottom: 1.5rem;
  }

  .motto {
    margin-bottom: 2.5rem;
  }
}

@media (max-width: 600px) {
  .values {
    gap: 0.5rem;
  }
  
  .values span {
    font-size: 0.75rem;
    padding: 0.5rem 0.85rem;
    letter-spacing: 1px;
  }
}
</style>