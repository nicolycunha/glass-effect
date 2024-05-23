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

input {
  width: 300px;
  height: 40px;
  font-size: 16px;
  padding: 2px 16px;
  border-radius: 8px;
}

input:active,
input:focus-visible {
  outline: none;
}
</style>