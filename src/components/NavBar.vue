<template>
  <div class="navContainer">
    <div class="logoContainer">
      <img class="logo" :src="GreenTechLogo" />
    </div>
  </div>
</template>

<script setup>
import GreenTechLogo from "@/assets/GreenTechLogo.png";
</script>

<style scoped>
.logo {
  height: auto;
  width: 140.14px;
}

.logoContainer {
  width: 310px;
  margin-top: 30px;
}

.navContainer {
  display: flex;
  justify-content: center;
}
</style>
