<template>
  <div class="field">
    <label>{{ field.text }}</label>
    <input
      v-model="field.value"
      :type="field.type"
      :placeholder="field.placeholder"
    />
  </div>
</template>

<script lang="ts">
import { IField } from "../interfaces/Field";

export default {
  name: "Field",
  props: {
    field: {
      type: Object as () => IField,
      required: true,
    },
  },
};
</script>

<style scoped>
.field {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  gap: 8px;
}

label {
  color: #1b1b1b;
}

input {
  width: 300px;
  height: 40px;
  font-size: 16px;
  padding: 2px 16px;
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.4);
  border: 1px solid rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(3px);
  color: #5f5f5f;
}

input:active,
input:focus-visible {
  border: 1px solid rgba(255, 255, 255, 0.4);
  outline: none;
}

input::placeholder {
  color: rgba(27, 27, 27, 0.3);
}
</style>