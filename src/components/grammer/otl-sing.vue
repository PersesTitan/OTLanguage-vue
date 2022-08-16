<template>
  <h1>연산자</h1>
  <h2 class="title" id="산술_연산자">산술 연산자</h2>
  <div v-for="l in list1" :key="l.key">
    <h3 class="head" :id="change(l.rescue)">{{ l.rescue }}</h3><br>
    문법 : <code>{{ l.grammar }}</code>
    <p>
      출시 버전 : {{ l.version }}<br>
      {{ l.explanation }}
    </p>
    예시<otl-code :value="l.example"/>
    출력<otl-code :value="l.print"/><br>
  </div>

  <h2 class="title" id="비교_연산자">비교 연산자</h2>
  <div v-for="l in list2" :key="l.key">
    <h3 class="head" :id="change(l.rescue)">{{ l.rescue }}</h3><br>
    문법 : <code>{{ l.grammar }}</code>
    <p>
      출시 버전 : {{ l.version }}<br>
      {{ l.explanation }}
    </p>
    예시<otl-code :value="l.example"/>
    출력<otl-code :value="l.print"/><br>
  </div>

  <h2 class="title" id="논리_연산자">논리 연산자</h2>
  <div v-for="l in list3" :key="l.key">
    <h3 class="head" :id="change(l.rescue)">{{ l.rescue }}</h3><br>
    문법 : <code>{{ l.grammar }}</code>
    <p>
      출시 버전 : {{ l.version }}<br>
      {{ l.explanation }}
    </p>
    예시<otl-code :value="l.example"/>
    출력<otl-code :value="l.print"/><br>
  </div>
</template>

<script>
import sing from '@/assets/json/sing.json'
import OtlCode from "@/components/edit/otl-code";

export default {
  name: "otl-sing",
  components: {OtlCode},
  data() {
    return {
      list1: sing.산술,
      list2: sing.비교,
      list3: sing.논리,
    }
  },
  methods: {
    change(value) {
      value = value.replaceAll("+", "1")
      value = value.replaceAll("-", "2")
      value = value.replaceAll("/", "3")
      value = value.replaceAll("*", "4")
      value = value.replaceAll("%", "5")

      value = value.replaceAll(">=", "9")
      value = value.replaceAll("<=", "10")
      value = value.replaceAll(">", "6")
      value = value.replaceAll("<", "7")
      value = value.replaceAll("=", "8")
      return value
    }
  }
}
</script>

<style scoped>
code {
  background: #f8f8f8;
  color: #d63200;
  padding: 3px 5px;
  margin: 0 2px;
  border-radius: 2px;
  white-space: nowrap;
}

h3.head {
  font-size: 120%;
  border-radius: 25px;
  padding: 0 5px;
  line-height: 2em;
  display: inline;
  color: green;
}

h2.title {
  border-bottom: 1px solid #ddd;
}
</style>