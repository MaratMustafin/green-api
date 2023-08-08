<script setup>
defineProps({
  label: String,
  output: String,
})

</script>

<template>
    <div>
        <label for="answer"> {{ label }}</label>
        <textarea name="answer" id="textarea" :value="output" readonly></textarea>
    </div>
</template>


<style scoped>
div {
    display: flex;
    flex-direction: column;
    padding: 1em;
    text-align: left;
}
label {
    padding-left: 20px;
    font-size: 1.8em;
    font-weight: 500;
}

textarea {
    height: 50vh;
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

</style>