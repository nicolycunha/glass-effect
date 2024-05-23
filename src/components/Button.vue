<template>
  <button class="button" type="button">
    <img class="icon" :src="button.image" :alt="button.text" />
    <span class="text">{{ button.text }}</span>
  </button>
</template>

<script lang="ts">
import { IButton } from "../interfaces/Button";

export default {
  name: "Button",
  components: {},
  props: {
    button: {
      type: Object as () => IButton,
      required: true,
    },
  },
  emits: ["loginMethod"],
  setup() {},
};
</script>

<style scoped>
.button {
  width: 300px;
  height: 40px;
  padding: 2px 16px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  border-radius: 8px;
}

.icon {
  height: 25px;
}
</style>