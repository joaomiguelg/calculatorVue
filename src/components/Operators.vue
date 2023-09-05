<script setup>
 const props = defineProps([ 'operator'

 ])
</script>
<template>
    <div class="row d-flex justify-content-center pt-3">
            <select class="col-1" @change="props.operator">
              <option value="add"> + </option>
              <option value="subtract"> - </option>
              <option value="multiply"> * </option>
              <option value="divide"> / </option>
            </select>
          </div>
</template>