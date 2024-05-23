<template>
  <button class="button-emphasis" type="button">
    <span class="text">Acessar conta</span>
    <font-awesome-icon :icon="['fas', 'arrow-right']" />
  </button>
</template>

<script lang="ts">
export default {};
</script>

<style scoped>
.button-emphasis {
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
  font-size: 16px;
}
</style>