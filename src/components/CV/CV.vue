<script>
import { useRoute } from 'vue-router'
import Experience from './Experience.vue'
import Education from './Education.vue'

export default {
  components: {
    Experience,
    Education,
  },

  data() {
    return {
      activeSection: 'experience',
    }
  },

  setup() {
    const route = useRoute()

    return {}
  },
}
</script>

<template>
  <h1>Dawid Jakieła</h1>
  <span>Junior Frontend Developer</span>
  <p>Mam na imię Dawid. bla bla bla</p>

  <section>
    <div>
      <button
        @click="activeSection = 'experience'"
        :class="{ active: activeSection === 'experience' }"
      >
        <h2>Doświadczenie zawodowe</h2>
      </button>

      <button
        @click="activeSection = 'education'"
        :class="{ active: activeSection === 'education' }"
      >
        <h2>Wykształcenie</h2>
      </button>
      <button
        @click="activeSection = 'skills'"
        :class="{ active: activeSection === 'skills' }"
      >
        <h2>Umiejętności</h2>
      </button>
      <button
        @click="activeSection = 'interests'"
        :class="{ active: activeSection === 'interests' }"
      >
        <h2>Zainteresowania</h2>
      </button>
    </div>
    <hr />
    <div class="content">
      <Experience v-if="activeSection === 'experience'" />
      <Education v-if="activeSection === 'education'" />
      <Skills v-if="activeSection === 'skills'" />
      <Interests v-if="activeSection === 'interests'" />
    </div>
  </section>
</template>

<style scoped>
button.active {
  font-weight: bold;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
