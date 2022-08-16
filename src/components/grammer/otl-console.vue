<template>
  <h1>콘솔</h1>
  <h2 class="title" id="기본_출력">기본 출력</h2>
  <h3 class="head" id="ㅅㅁㅅ">ㅅㅁㅅ</h3><br>
  문법 : <code>ㅅㅁㅅ &lt;출력 내용&gt;</code><br>
  <p>
    출시 버전 : 1.0.0<br>
    출력 내용을 출력하는 동작을 합니다.<br>
  </p>
  예시<otl-code value="ㅅㅁㅅ 안녕\nㅅㅁㅅ 하세요?"/>
  출력<otl-code value="안녕하세요?"/>
  <br>
  <h3 class="head" id="ㅆㅁㅆ">ㅆㅁㅆ</h3><br>
  문법 : <code>ㅆㅁㅆ &lt;출력 내용&gt;</code><br>
  <p>
    출시 버전 : 1.0.0<br>
    출력 내용과 줄바꿈이 존재하는 동작을 합니다.<br>
  </p>
  예시<otl-code value="ㅆㅁㅆ 안녕\nㅆㅁㅆ 하세요?"/>
  출력<otl-code value="안녕\n하세요?"/>
  <br>

  <h2 class="title" id="강제_출력">강제 출력</h2>
  <h3 class="head" id="ㅅㅁㅅ2">!ㅅㅁㅅ!</h3><br>
  문법 : <code>!ㅅㅁㅅ! &lt;출력 내용&gt;</code><br>
  <p>
    출시 버전 : 2.0.0<br>
    출력 내용을 출력하는 동작을 합니다.<br>
    하지만 변수나 특정 값이 들어가야하는 문법을 무시하고 출력내용 그대로 출력하게 됩니다.<br>
  </p>
  예시<otl-code value="!ㅅㅁㅅ! 안녕\n!ㅅㅁㅅ! 하세요?:ㅅㅇㅅ_"/>
  출력<otl-code value="안녕하세요?:ㅅㅇㅅ_"/>
  <br>
  <h3 class="head" id="ㅆㅁㅆ2">!ㅆㅁㅆ!</h3><br>
  문법 : <code>!ㅆㅁㅆ! &lt;출력 내용&gt;</code><br>
  <p>
    출시 버전 : 2.0.0<br>
    출력 내용과 줄바꿈이 존재하는 동작을 합니다.<br>
    하지만 변수나 특정 값이 들어가야하는 문법을 무시하고 출력내용 그대로 출력하게 됩니다.<br>
  </p>
  예시<otl-code value="!ㅆㅁㅆ! 안녕\n!ㅆㅁㅆ! 하세요?:ㅅㅇㅅ_"/>
  출력<otl-code value="안녕\n하세요?:ㅅㅇㅅ_"/>
  <br>

  <h2 class="title" id="입력">입력</h2>
  <h3 class="head" id="ㅅㅇㅅ">ㅅㅇㅅ</h3><br>
  문법 : <code>:ㅅㅇㅅ_</code> 또는 <code>:ㅅㅇㅅ[공백]</code><br>
  <p>
    출시 버전 : 1.0.0<br>
    출력 내용과 줄바꿈이 존재하는 동작을 합니다.<br>
    하지만 변수나 특정 값이 들어가야하는 문법을 무시하고 출력내용 그대로 출력하게 됩니다.<br>
  </p>
  예시<otl-code value="ㅆㅁㅆ :ㅅㅇㅅ_\n입력: 안녕"/>
  출력<otl-code value="안녕"/>
  <br>
</template>

<script>
import OtlCode from "@/components/edit/otl-code";
export default {
  name: "otl-gra",
  components: {OtlCode}
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