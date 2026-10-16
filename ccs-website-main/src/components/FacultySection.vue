<template>
  <section class="faculty" id="faculty">
    <div class="container">
      <div class="section-header">
        <p class="subheading">The People Behind CCS</p>
        <h2>Faculty & Staff</h2>
        <div class="gold-line"></div>
      </div>

      <div class="group">
        <h3 class="group-title">College Dean</h3>
        <div class="card-row single">
          <div class="person-card dean-card">
            <div class="avatar-wrapper">
              <img :src="deanImg" alt="Dean Quijano" />
            </div>
            <h4>Ma. Christina A. Quijano, MSCS</h4>
            <p class="role">College Dean</p>
          </div>
        </div>
      </div>

      <div class="group">
        <h3 class="group-title">Department Heads & Coordinators</h3>
        <div class="card-row">
          <div class="person-card" v-for="(p, i) in heads" :key="i">
            <div class="avatar-wrapper">
              <img :src="getImg(p.img)" :alt="p.name" />
            </div>
            <h4>{{ p.name }}</h4>
            <p class="role">{{ p.role }}</p>
          </div>
        </div>
      </div>

      <div class="group">
        <h3 class="group-title">Faculty Members</h3>
        <div class="card-row">
          <div class="person-card" v-for="(p, i) in faculty" :key="i">
            <div class="avatar-wrapper">
              <img :src="getImg(p.img)" :alt="p.name" />
            </div>
            <h4>{{ p.name }}</h4>
            <p class="role">{{ p.duty }}</p>
          </div>
        </div>
      </div>

      <div class="group">
        <h3 class="group-title">Administrative Staff</h3>
        <div class="card-row">
          <div class="person-card" v-for="(p, i) in staff" :key="i">
            <div class="avatar-wrapper">
              <img :src="getImg(p.img)" :alt="p.name" />
            </div>
            <h4>{{ p.name }}</h4>
            <p class="role">{{ p.position }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import deanImg from '@/assets/images/dean.png'

const getImg = (filename) => new URL(`/src/assets/images/${filename}`, import.meta.url).href

const heads = ref([
  { name: 'Rea P. Balontong, MBA', role: 'Dept Head (IT & IS)', img: 'rea.jpg' },
  { name: 'Marjee Rose B. Parreño, MSCS, MBA', role: 'Coord (BSCS, BSDMIA, MSCS)', img: 'marjee.jpg' },
  { name: 'Ana Mae B. Cantel, MLIS', role: 'Coord (BLIS, MLIS)', img: 'ana.jpg' },
  { name: 'Lennon D. Pajar', role: 'Lab Coordinator', img: 'lennon.jpg' }
])

const faculty = ref([
  { name: 'Leo Paulo B. Beldia', duty: 'BSIT & BSIS', img: 'leo.jpg' },
  { name: 'Pedro Peter Rhys B. Cambronero, MSCS', duty: 'BSCS', img: 'pedro.jpg' },
  { name: 'Lesley Joy L. Dignadice, MBA', duty: 'BSIT & BSIS', img: 'lesley.jpg' },
  { name: 'Rodolfo C. Eregia, Jr', duty: 'BSIT & BSIS', img: 'rod.jpg' },
  { name: 'Donie S. Jardeleza, MSCS', duty: 'BSIT & BSIS', img: 'donie.jpg' },
  { name: 'Antonio M. Montaño, Jr.', duty: 'BSIT & BSIS', img: 'antonio.jpg' },
  { name: 'Rose Leah Joy A. Ojacastro, MSCS', duty: 'BSIT & BSIS', img: 'rose.jpg' },
  { name: 'Ma. Sheila C. Sapul, Ph.D.', duty: 'BSCS', img: 'sheila.jpg' }
])

const staff = ref([
  { name: 'Chrislyn C. Castaño', position: 'Secretary', img: 'chrislyn.jpg' },
  { name: 'A.M.P. Latter P. Taasan', position: 'Lab Technician', img: 'latter.jpg' },
  { name: 'Chriselda Elaine Ador', position: 'Guidance Counselor', img: 'chriselda.jpg' },
  { name: 'Donna May Rivera', position: 'Library Liaison Officer', img: 'donna.png' }
])
</script>

<style scoped>
.faculty {
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

.group {
  margin-bottom: 4rem;
}

.group:last-child {
  margin-bottom: 0;
}

.group-title {
  color: #1e293b;
  font-size: 1.25rem;
  font-weight: 700;
  margin-bottom: 1.75rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #e2e8f0;
  position: relative;
}

.group-title::after {
  content: "";
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 40px;
  height: 2px;
  background: #b8860b;
}

.card-row {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
  width: 100%;
}

.card-row.single {
  grid-template-columns: 1fr;
  max-width: 320px;
  margin: 0 auto;
}

.person-card {
  background: #ffffff;
  border: 1px solid #f1f5f9;
  border-radius: 16px;
  padding: 2rem 1.25rem;
  text-align: center;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.02), 0 2px 4px -2px rgba(0, 0, 0, 0.02);
  display: flex;
  flex-direction: column;
  align-items: center;
}

.person-card:hover {
  transform: translateY(-4px);
  border-color: #e2e8f0;
  box-shadow: 0 12px 20px -5px rgba(0, 0, 0, 0.06), 0 4px 6px -2px rgba(0, 0, 0, 0.03);
}

.dean-card {
  border-top: 3px solid #b8860b;
}

.avatar-wrapper {
  width: 110px;
  height: 110px;
  border-radius: 50%;
  padding: 3px;
  border: 2px solid #e2e8f0;
  margin-bottom: 1.25rem;
  transition: border-color 0.3s ease;
}

.person-card:hover .avatar-wrapper {
  border-color: #b8860b;
}

.avatar-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
}

.person-card h4 {
  color: #1e293b;
  font-size: 0.975rem;
  font-weight: 700;
  margin: 0 0 0.4rem;
  line-height: 1.35;
}

.role {
  color: #64748b;
  font-size: 0.85rem;
  font-weight: 500;
  margin: 0;
  line-height: 1.4;
}

@media (max-width: 1024px) {
  .card-row {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 768px) {
  .faculty {
    padding: 4rem 1rem;
  }

  .card-row {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .person-card {
    padding: 1.5rem 1rem;
  }
}

@media (max-width: 480px) {
  .card-row {
    grid-template-columns: 1fr;
  }
}
</style>