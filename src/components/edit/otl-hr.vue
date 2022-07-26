<template>
  <p/>
  <div class="hr-size">
    <div class="hr-sect" :id="id">
      <h2><slot/></h2>
    </div>
  </div>
  <p/>
</template>

<script>
export default {
  name: "otl-hr",
  data() {
    return {
      "margin": {
        type: Number,
        default: 0
      }
    }
  },
  props: {
    id: {
      type: String
    }
  }
}
</script>

<style scoped>
.hr-sect {
  display: flex;
  flex-basis: 100%;
  align-items: center;
  /*color: rgba(0, 0, 0, 0.35);*/
  /*font-size: 12px;*/
  color: black;
  margin: 8px 0;
}

.hr-sect::before, .hr-sect::after {
  content: "";
  flex-grow: 1;
  background: rgba(0, 0, 0, 0.35);
  height: 1px;
  font-size: 0;
  line-height: 0;
  margin: 0 30px;
}

.hr-size {
  width: 90%;
  margin: auto;
}
</style>