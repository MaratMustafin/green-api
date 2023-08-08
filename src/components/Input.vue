<script setup>
import { ref } from "vue";

const model = ref();
defineProps({
  type: String,
  label: String,
  placeholder: String,
});
</script>

<template>
    <label v-show="label"> {{  label }}</label>
    <input :type="type" 
        :placeholder="placeholder"
        v-model="model"
        @input="$emit('update:modelValue', model)"
        required>
</template>


<style scoped>
input {
  border-radius: 8px;
  border: 2px solid #4cae4f;
  padding: 0.6em 1.2em;
  margin: 0.6em;
  font-size: 1.2em;
  font-weight: 500;
  font-family: inherit;
  background-color: white;
  cursor: pointer;
  transition: border-color 0.25s;
}
input:hover {
  border-color: #64ff86;
}
input:focus,
input:focus-visible {
  outline: 2px auto gold;
}
</style>