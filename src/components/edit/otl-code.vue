<template>
  <p class="code-pos">
    <code>
      <slot/>
    </code>
    <code v-html="changeColor"/>
  </p>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ""
    }
  },
  computed: {
    changeColor() {
      let values = this.value;
      const patterns1 = ["ㅅㅁㅅ", "ㅆㅁㅆ", "!ㅆㅁㅆ!", "!ㅅㅁㅅ!", "ㅅㅇㅅ"];
      const patterns2 = [
        "ㅇㅈㅇ", "ㅇㅉㅇ", "ㅇㅂㅇ", "ㅇㅁㅇ", "ㅇㄱㅇ", "ㅇㅅㅇ", "ㅇㅆㅇ",
        "ㄹㅈㄹ", "ㄹㅉㄹ", "ㄹㅂㄹ", "ㄹㅁㄹ", "ㄹㄱㄹ", "ㄹㅅㄹ", "ㄹㅆㄹ",
        "ㅇ+ㅇ", "ㅇ-ㅇ", "ㅇ/ㅇ", "ㅇ*ㅇ", "ㅇ%ㅇ", "ㅇ>ㅇ", "ㅇ<ㅇ", "ㅇ=ㅇ",
        "ㅇ>=ㅇ", "ㅇ<=ㅇ", "oio", "oIo", "obo", "oCo", "oco", "ofo", "oFo",
        "lil", "lIl", "lbl", "lCl", "lcl", "lfl", "lFl"];
      const patterns3 = ["ㄲㅌㄲ", "ㅜㅅㅜ", "ㅡ_ㅡ", "@ㅂ@", "@ㅆ@", "@ㅅ@", "@ㅈ@", "@ㅉ@", "?ㅅ?", "ㅋㄹㅋ"];
      const patterns4 = ["ㄷㅇㄷ", "?ㄷㅇㄷ?", "ㄷㅇㄷ~ㅋㄹㅋ", "ㅋㅅㅋ", "ㅍㅅㅍ", "ㅁㅅㅁ"]

      values = values.replaceAll(" ", "&nbsp;")
      values = values.replaceAll("\\n", "<br>")
      values = values.replaceAll("otl", `<span style="color: forestgreen">otl</span>`)

      patterns1.forEach(pattern =>
          values = values.replaceAll(pattern, `<span style="color: mediumpurple; font-weight: bolder">${pattern}</span>`))
      patterns2.forEach(pattern =>
        values = values.replaceAll(pattern, `<span style="color: darkorange; font-weight: bolder">${pattern}</span>`))
      patterns3.forEach(pattern =>
        values = values.replaceAll(pattern, `<span style="color: yellow; font-weight: bolder">${pattern}</span>`))
      patterns4.forEach(pattern =>
        values = values.replaceAll(pattern, `<span style="color: yellowgreen">${pattern}</span>`))

      return values.toString()
    }
  }
}

</script>
<style scoped>
p.code-pos {
  display: flex;
  background: #1b1f23;
  border-radius: 10px;
  padding: 20px;
  overflow: auto;
  white-space: nowrap;
  color: white;
}

p.code-pos > code {
  text-align: left;
}
</style>