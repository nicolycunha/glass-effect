<template>
  <button class="button" type="button">
    <span class="text">Acessar conta</span>
    <font-awesome-icon :icon="['fas', 'arrow-right']" />
  </button>
</template>

<script lang="ts">
export default {};
</script>

<style scoped>
.button {
  width: 300px;
  height: 40px;
  padding: 2px 16px;
  margin: 10px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  border-radius: 8px;
  font-family: "IBM Plex Sans", Inter, sans-serif;
  background: rgb(255, 144, 0);
  background: linear-gradient(
    90deg,
    rgba(255, 144, 0, 1) 0%,
    rgba(255, 27, 107, 1) 100%
  );
  border: 1px solid rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(5px);
  color: #fff;
  font-size: 16px;
}
</style>