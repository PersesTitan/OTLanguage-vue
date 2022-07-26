<template>
  <span class="p">
    <slot/>
  </span>
</template>

<script>
export default {
  name: "otl-p"
}
</script>

<style scoped>
.p {
  color: mediumpurple;
  font-weight: bolder;
}
</style>