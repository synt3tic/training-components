<template>
  <div class="app">
    <vehicle-information />
  </div>
</template>

<script>
import VehicleInformation from "./components/VehicleInformation.vue";

export default {
  components: {
    VehicleInformation
  }
}
</script>

<style>
.app {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 50px;
}
</style>
