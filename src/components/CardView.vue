<template>
  <div class="card">
    <div class="card-image" :style="{ backgroundImage: `url(${imagen})` }">
    </div>
    <div class="card-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["imagen"],
}
</script>

<style scoped>


.card-image {
  background-size: cover;
  background-position: center;
  height: 180px;
  width: 200px;
}
</style>
