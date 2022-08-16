<template>
  <div class="text">
    <h2>OTLanguage</h2>
    <h3 v-on:click="scrollTop(consoleLink)">콘솔</h3>
    <a v-on:click="scroll('#기본_출력', consoleLink)">기본 출력</a><br>
    <div v-if="path === console">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅅㅁㅅ', consoleLink)">ㅅㅁㅅ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅆㅁㅆ', consoleLink)">ㅆㅁㅆ</a><br>
      <br>
    </div>
    <a v-on:click="scroll('#강제_출력', consoleLink)">강제 출력</a><br>
    <div v-if="path === console">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅅㅁㅅ2', consoleLink)">!ㅅㅁㅅ!</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅆㅁㅆ2', consoleLink)">!ㅆㅁㅆ!</a><br>
      <br>
    </div>
    <a v-on:click="scroll('#입력', consoleLink)">입력</a><br>
    <div v-if="path === console">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅅㅇㅅ', consoleLink)">ㅅㅇㅅ</a><br>
      <br>
    </div>

    <h3 v-on:click="scrollTop(variableLink)">변수</h3>
    <a v-on:click="scroll('#기본_타입', variableLink)">기본 타입</a><br>
    <div v-if="path === variable">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅈㅇ', variableLink)">ㅇㅈㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅉㅇ', variableLink)">ㅇㅉㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅂㅇ', variableLink)">ㅇㅂㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅁㅇ', variableLink)">ㅇㅁㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㄱㅇ', variableLink)">ㅇㄱㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅅㅇ', variableLink)">ㅇㅅㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅆㅇ', variableLink)">ㅇㅆㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#변수값_가져오기', variableLink)">변수값 가져오기</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#변수값_업데이트', variableLink)">변수값 업데이트</a><br>
      <br>
    </div>
    <a v-on:click="scroll('#리스트_타입', variableLink)">리스트 타입</a><br>
    <div v-if="path === variable">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㅈㄹ', variableLink)">ㄹㅈㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㅉㄹ', variableLink)">ㄹㅉㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㅂㄹ', variableLink)">ㄹㅂㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㅁㄹ', variableLink)">ㄹㅁㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㄱㄹ', variableLink)">ㄹㄱㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㅅㄹ', variableLink)">ㄹㅅㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄹㅆㄹ', variableLink)">ㄹㅆㄹ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#값_추가', variableLink)">값 추가</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#값_가져오기', variableLink)">값 가져오기</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#값_삭제', variableLink)">값 삭제</a><br>
    </div>

    <h3 v-on:click="scrollTop('#클래스')">클래스 & 메소드</h3>
    <a v-on:click="scroll('#클래스', classLink)">클래스</a><br>
    <div v-if="path === this.class">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅋㅅㅋ', classLink)">ㅋㅅㅋ</a><br>
      <br>
    </div>
    <a v-on:click="scroll('#메소드', classLink)">메소드</a><br>
    <div v-if="path === this.class">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅁㅅㅁ', classLink)">ㅁㅅㅁ</a><br>
      <br>
    </div>

    <h3 v-on:click="scrollTop(singLink)">연산자</h3>
    <a v-on:click="scroll('#산술_연산자', singLink)">산술 연산자</a><br>
    <div v-if="path === sing">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ1ㅇ', singLink)">ㅇ+ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ2ㅇ', singLink)">ㅇ-ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ3ㅇ', singLink)">ㅇ/ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ4ㅇ', singLink)">ㅇ*ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ5ㅇ', singLink)">ㅇ%ㅇ</a><br>
      <br>
    </div>
    <a v-on:click="scroll('#비교_연산자', singLink)">비교 연산자</a><br>
    <div v-if="path === sing">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ6ㅇ', singLink)">ㅇ&gt;ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ7ㅇ', singLink)">ㅇ&lt;ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ8ㅇ', singLink)">ㅇ=ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ9ㅇ', singLink)">ㅇ&gt;=ㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇ10ㅇ', singLink)">ㅇ&lt;=ㅇ</a><br>
      <br>
    </div>
    <a v-on:click="scroll('#논리_연산자', singLink)">논리 연산자</a><br>
    <div v-if="path === sing">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅇ', singLink)">ㅇㅇ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄴㄴ', singLink)">ㄴㄴ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㄴ', singLink)">ㅇㄴ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄸ', singLink)">ㄸ</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄲ', singLink)">ㄲ</a><br>
      <br>
    </div>

    <!-- Poison -->
    <h2>Poison</h2>
    <h3 v-on:click="scrollTop(dataBaseLink)">데이터베이스</h3>
    <a v-on:click="scroll('#데이터베이스_클래스', dataBaseLink)">데이터베이스 클래스</a><br>
    <div v-if="path === dataBase">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄷㅇㄷ1', dataBaseLink)">?ㄷㅇㄷ?</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄷㅇㄷ6', dataBaseLink)">ㄷㅇㄷ[][][][][][]</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㄷㅇㄷ3', dataBaseLink)">ㄷㅇㄷ[][][]</a><br><br>
    </div>
    <a v-on:click="scroll('#데이터베이스_메소드', dataBaseLink)">데이터베이스 메소드</a><br>
    <div v-if="path === dataBase">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅋㄹㅋ1', dataBaseLink)">ㄷㅇㄷ~ㅋㄹㅋ[]</a><br>
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅋㄹㅋ2', dataBaseLink)">ㄷㅇㄷ~ㅋㄹㅋ[][]</a><br><br>
    </div>
    <h3 v-on:click="scrollTop(web)">웹</h3>
    <a v-on:click="scroll('#웹_세팅', web)">웹 세팅</a><br>
    <div v-if="path === web">
      &nbsp;&nbsp;<a v-on:click="scroll('#ㅇㅅㅇ1', web)">&lt;ㅇㅅㅇ&gt;</a><br><br>
    </div>

    <h2>Music</h2>

  </div>
  <div style="height: 70px"/>
</template>

<script>
export default {
  name: "grammer-list",
  data() {
    return {
      path : window.location.pathname.split('/')[4], // sing, console, variable, ...
      console: "console",
      variable: "variable",
      class: "class",
      sing: "sing",
      dataBase: "database",
      web: "web",
      consoleLink: "/OTLanguage/grammar/console",
      variableLink: "/OTLanguage/grammar/variable",
      classLink: "/OTLanguage/grammar/class",
      singLink: "/OTLanguage/grammar/sing",
      dataBaseLink: "/Poison/grammar/database",
      webLink: "/Poison/grammar/web"
    }
  },
  methods: {
    scroll(id, link) {
      if (location.pathname !== link) location.href = link
      const height = document.querySelector(id).offsetHeight * 3
      const position = document.querySelector(id).offsetTop
      window.scrollTo({top:position - height, behavior:'smooth'})
    },
    scrollTop(link) {
      if (location.pathname !== link) location.href = link
      window.scrollTo(0, 0)
    }
  }
}
</script>

<style scoped>
div.text {
  margin: auto;
  text-align: left;
  width: 90%;
}

div.text > a:hover {
  color: #dddddd;
}

div.text > div > a:hover {
  color: #dddddd;
}
</style>