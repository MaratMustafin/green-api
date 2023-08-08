<script setup>
defineProps({
  text: String,
})
</script>

<template>
    <button>
        {{ text }}
    </button>
</template>


<style>
button {
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

button:hover {
  border-color: #64ff86;
}
button:focus,
button:focus-visible {
  outline: 2px auto gold;
}
</style>