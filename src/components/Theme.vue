<template>
  <label for="checkbox" class="switch">
    <input type="checkbox" id="checkbox" v-model="checked" />
    <div class="slider round">
      <font-awesome-icon v-if="!checked" :icon="['far', 'fa-sun']" />
      <font-awesome-icon v-else :icon="['far', 'fa-moon']" />
    </div>
  </label>
</template>

<script lang="ts">
import { ref, watch } from "vue";
import "../styles/theme.css";

export default {
  name: "Theme",
  setup() {
    const checked = ref<Boolean>(false);

    watch(checked, async (_) => {
      document.body.className = checked.value ? "dark-mode" : "light-mode";
    });

    return {
      checked,
    };
  },
};
</script>

<style scoped>
.switch {
  display: incline-block;
  height: 34px;
  width: 60px;
  position: absolute;
  top: 10px;
  right: 10px;
}

.switch input {
  display: none;
}

.slider {
  background-color: #ccc;
  bottom: 0;
  cursor: pointer;
  left: 0;
  position: absolute;
  right: 0;
  top: 0;
  transition: 0.4s;
}

.slider:before {
  background-color: #fff;
  bottom: 4px;
  content: "";
  height: 26px;
  left: 4px;
  position: absolute;
  transition: 0.4s;
  width: 26px;
}

input:checked + .slider {
  background-color: #535156;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

.fa-sun {
  margin: 6px 0 0 23px;
}

.fa-sun,
.fa-moon {
  font-size: 20px;
}

.fa-moon {
  margin: 6px 23px 0 0;
}
</style>