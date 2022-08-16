<template>
  <h1>클래스 & 메소드</h1>
  <b>참고</b>
  <p>
    클래스는 이미 정의되어 있는 ㄷㅇㄷ, ㅁㅇㅁ등 예약된 클래스가 존재하니 주의해주세요.<br>
    상위 변수에 접근할려고 할때는 ~를 이용해서 접근이 가능합니다. 예시는 다음과 같이 사용할 수 있습니다.
  </p>
  <b>코드</b>
  <otl-code value="ㅇㅁㅇ 전체변수:전체변수\nㅋㅅㅋ 클래스변수[ㅇㅁㅇ 클래스변수] {\n    ㅆㅁㅆ\n    ㅆㅁㅆ 클래스변수\n    ㅆㅁㅆ :~전체변수_\n
    ㅆㅁㅆ :클래스변수_\n\n    ㅁㅅㅁ 메소드변수[ㅇㅁㅇ 메소드변수] {\n        ㅆㅁㅆ\n        ㅆㅁㅆ 메소드변수\n        ㅆㅁㅆ :~~전체변수_\n
        ㅆㅁㅆ :~클래스변수_\n        ㅆㅁㅆ :메소드변수_\n    }\n}\n\n클래스변수[클래스변수]\n클래스변수~메소드변수[메소드변수]"/>
  <b>출력</b>
  <otl-code value="\n클래스변수\n전체변수\n클래스변수\n\n메소드변수\n전체변수\n클래스변수\n메소드변수"/>
  <br>

  <h2 class="title" id="클래스">클래스</h2>
  <h3 class="head" id="ㅋㅅㅋ">ㅋㅅㅋ</h3><br>
  문법 : <code>ㅋㅅㅋ &lt;클래스명&gt;[&lt;변수타입&gt; &lt;변수명&gt;][...] {...}</code><br>
  <p>
    출시 버전 : 2.3.0<br>
    클래스를 생성하는 동작을 합니다. 클래스를 정의할때는 매걔변수가 최소 1개 이상 존재해야합니다.
  </p>
  예시<otl-code value="ㅋㅅㅋ 테스트[ㅇㅁㅇ 변수] {\n&nbsp;&nbsp;&nbsp;ㅆㅁㅆ :변수_\n}\n\n테스트[출력]"/>
  출력<otl-code value="출력"/><br>

  <h2 class="title" id="메소드">메소드</h2>
  <h3 class="head" id="ㅁㅅㅁ">ㅁㅅㅁ</h3><br>
  문법 : <code>ㅁㅅㅁ 메소드[ㅇㅁㅇ 변수][...] {...}</code><br>
  <p>
    출시 버전 : 2.3.0<br>
    클래스와 동일하게 메소드 또한 1개 이상의 매개변수가 있어야 합니다.<br>
    만약 특정 클래스 안에 존재하는 메소드라면 먼저 클래스를 1번이상 실행하고 메소드를 생성해야합니다.<br><br>
    메소드는 종류가 2가지 있습니다. 중괄호 마지막에 <u>'=>메소드명'</u>를 붙치면 메소드값을 반환하는 메소드로 인식되고,
    붙치지 않을 경우 아무것도 반환하지 않는 메소드로 인식됩니다.<br>
    클래스안에 메소드가 존재할시 <u>'&lt;클래스명&gt;~&lt;메소드명&gt;'</u>형태로 메소드를 꺼내올수 있습니다.
  </p>
  <b>코드</b>
  <otl-code value="ㅁㅅㅁ 전체메소드[ㅇㅁㅇ 변수] {\n    ㅆㅁㅆ :변수_\n}\n\nㅋㅅㅋ 테스트[ㅇㅁㅇ 변수] {\n    ㅁㅅㅁ 메소드1[ㅇㅁㅇ 안녕] {\n
        ㅆㅁㅆ :안녕_\n    }\n\n    ㅁㅅㅁ 메소드2[ㅇㅁㅇ 아] {\n        ㅇㅁㅇ ㅁ:1234\n    }=>아\n}
        \n\n전체메소드[출력1]\n테스트[ ]\n테스트~메소드1[출력2]\nㅆㅁㅆ :테스트~메소드2[출력3]_\n"/>
  <b>출력</b>
  <otl-code value="출력1\n출력2\n출력3\n"/>
  <br>

</template>

<script>
import OtlCode from "@/components/edit/otl-code";
export default {
  name: "otl-class",
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