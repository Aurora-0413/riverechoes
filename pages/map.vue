<script setup lang="ts">

</script>

<template>
  <div class="background">
    <RouterLink to="/costume"><button>梳妆</button></RouterLink>
    <RouterLink to="/craft"><button>工艺</button></RouterLink>
    <RouterLink to="/show"><button>表演</button></RouterLink>
    <RouterLink to="/exhibition"><button>展览</button></RouterLink>
    <RouterLink to="/ritual"><button>祭祀</button></RouterLink>
    <RouterLink to="/museum"><button>博物馆</button></RouterLink>
  </div>
</template>

<style scoped>
.background {
  background-image: url('/assets/map.webp');
}

.background a {
  position: absolute;
}

.background a:nth-child(1) {
  top: 30%;
  left: 20%;
}

.background a:nth-child(2) {
  top: 20%;
  left: 70%;
}

.background a:nth-child(3) {
  top: 60%;
  left: 40%;
}

.background a:nth-child(4) {
  top: 75%;
  left: 10%;
}

.background a:nth-child(5) {
  top: 90%;
  left: 70%;
}


.background a:nth-child(6) {
  top: 55%;
  left: 80%;
}
</style>