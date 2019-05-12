<template>
  <div class="output text-success">
    <span>{{ translatedText }}</span>
  </div>
</template>

<script>

export default {
  name: 'translateOutput',
  props:['translatedText']
}

</script>

<style>
    .output {
        font-size: 30px;
    }
</style>
