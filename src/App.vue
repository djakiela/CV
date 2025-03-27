<script setup>
import CV from './components/CV/CV.vue'
import Content from './components/common/RightContent/Content.vue'
</script>

<template>
  <body>
    <CV />
    <Content />
  </body>

  <footer>
    <p>© 2025. Wszelkie prawa zastrzeżone</p>
  </footer>
</template>

<style scoped>
@media (min-width: 576px) {
  /* Styles for small devices (phones) */
}

@media (min-width: 768px) {
  /* Styles for medium devices (tablets) */
}

@media (min-width: 992px) {
  /* Styles for large devices (desktops) */
}

body {
  font-family: Arial, Helvetica, sans-serif;
  display: flex;
}

footer {
  justify-content: flex-end;
}
</style>
