<template>
  <span class="g">
    <slot/>
  </span>
</template>

<script>
export default {
  name: "otl-g"
}
</script>

<style scoped>
.g {
  color: forestgreen;
  font-weight: bolder;
}
</style>