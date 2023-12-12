<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
  </div>
</template>

<style scoped>

@font-face {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 800;
  src: local('Montserrat ExtraBold'), local('Montserrat-ExtraBold'),
       url(https://fonts.gstatic.com/s/montserrat/v15/JTUSjIg1_i6t8kCHKm459Wlhzg.ttf) format('truetype');
}

h1 {
  font-family: 'Montserrat', sans-serif;
  font-weight: 800;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
