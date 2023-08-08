<script setup>
import { ref } from "vue";

const model = ref();
defineProps({
  label: String,
  placeholder: String
})

</script>

<template>
    <label for="answer"> {{ label }}</label>
    <textarea name="answer" id="textarea" v-model="model"
        @input="$emit('update:modelValue', model)" :placeholder="placeholder"></textarea>
</template>


<style scoped>
textarea {
    height: 150px;
    resize: none;
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
textarea:focus,
textarea:focus-visible {
  outline: 2px auto gold;
}

</style>