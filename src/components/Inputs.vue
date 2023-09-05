<script setup>

const props = defineProps(['value1', 'value2'])

</script>
<template>
    <div class="row gap-5 d-flex justify-content-center">
        <input type="text" placeholder="Insert your first number" class="col-3" @keyup="props.value1">
        <input type="text" placeholder="Insert your second number" class="col-3" @keyup="props.value2">
    </div>
</template>


