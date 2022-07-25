<template>
  <h1>Download</h1>
  <div class="download">

  </div>
</template>

<script>
export default {
  props: {
    downloadLink: {
      type: String,
      default: "curl https://raw.githubusercontent.com/OTLanguage/.github/main/otlmake.sh | sh"
    }
  }
}
</script>

<style scoped>
  .download {
    background: gray;
    width: 20px;
  }
</style>