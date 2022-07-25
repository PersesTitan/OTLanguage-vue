<template>
  <p class="code-pos">
    <code>
      <slot/>
    </code>
  </p>
</template>

<script>
</script>

<style scoped>
.code-pos {
  display: flex;
  background: lightgray;
  border-radius: 10px;
  padding: 20px;
  overflow: auto;
  white-space: nowrap;
}
</style>