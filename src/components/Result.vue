<script setup>

    const props = defineProps(['calcular'])

</script>
<template>
   <div class="text-center pt-3">
          <h3>Result: {{props.calcular}}</h3>
        </div>
</template>