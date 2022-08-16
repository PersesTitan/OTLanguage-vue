<template>
  <h1>변수</h1>
  <h2 class="title" id="기본_타입">기본 타입</h2>
  <p>
    <b>참고</b><br>
    기본적으로 ㅇㅁㅇ(문자형 (으))로 저장해도 동작에는 문제없지만 타입을 지정해주면 생기는 장점이 있습니다.<br>
    타입을 지정해주면 타입이 맞는지 확인을 하는 동작을 하는데 만약 타입이 일치하지 않으면 에러를 발생하기 때문에 변수값에 대한
  </p>

  <div v-for="list in listNormal" :key="list.key">
    <h3 class="head" :id="this.changeEnter(list.rescue)">{{ list.rescue }}</h3><br>
    문법 : <code>{{ list.grammar }}</code>
    <p>
      출시 버전 : {{ list.version }}<br>
      {{ list.explanation }}
    </p>
    예시<otl-code :value="list.example"/>
    출력<otl-code :value="list.print"/><br>
  </div>

  <h2 class="title" id="리스트_타입">리스트 타입</h2>
  <div v-for="list in listList" :key="list.key">
    <h3 class="head" :id="this.changeEnter(list.rescue)">{{ list.rescue }}</h3><br>
    문법 : <code>{{ list.grammar }}</code>
    <p>
      출시 버전 : {{ list.version }}<br>
      {{ list.explanation }}
    </p>
    예시<otl-code :value="list.example"/>
    출력<otl-code :value="list.print"/><br>
  </div>
</template>

<script>
import OtlCode from "@/components/edit/otl-code";
import variable from '@/assets/json/variable.json'

export default {
  name: "otl-variable",
  components: {OtlCode},
  data() {
    return {
      listNormal: variable.normal,
      listList: variable.list
    }
  },
  methods: {
    changeEnter(value) {
      return value.replaceAll(' ', "_")
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