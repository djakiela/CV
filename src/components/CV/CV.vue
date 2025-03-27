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
  <body class="content">
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
        <hr />
        <Experience v-if="activeSection === 'experience'" />

        <button
          @click="activeSection = 'education'"
          :class="{ active: activeSection === 'education' }"
        >
          <h2>Wykształcenie</h2>
        </button>
        <hr />
        <Education v-if="activeSection === 'education'" />
        <button
          @click="activeSection = 'skills'"
          :class="{ active: activeSection === 'skills' }"
        >
          <h2>Umiejętności</h2>
        </button>
        <hr />
        <Skills v-if="activeSection === 'skills'" />
        <button
          @click="activeSection = 'interests'"
          :class="{ active: activeSection === 'interests' }"
        >
          <h2>Zainteresowania</h2>
        </button>
        <hr />
        <Interests v-if="activeSection === 'interests'" />
      </div>
    </section>
  </body>
</template>

<style scoped>
button.active {
  font-weight: bold;
}

button {
  background: none;
  border: none;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
