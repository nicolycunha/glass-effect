<template>
  <label for="checkbox" class="switch">
    <input type="checkbox" id="checkbox" v-model="checked" />
    <div class="slider round"></div>
  </label>
</template>

<script>
export default {
  name: "Theme",
};
</script>

<style scoped>
.switch {
  display: incline-block;
  height: 34px;
  position: relative;
  width: 60px;
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
</style>