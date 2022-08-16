<template>
  <h1>데이터베이스</h1>
  <b>참고</b><br>
  ㄷㅇㄷ는 데이터베이스에서 사용하고 있는 예약된 클래스명이므로 클래스명으로 생성이 불가능합니다.<br>
  <b>예시</b>
  <otl-code value="?ㅅ? :?ㄷㅇㄷ?[org.h2.Driver]_ {
  \n    ㄷㅇㄷ[jdbc:h2:tcp://localhost/~/test][sa][ ]
  \n    ㄷㅇㄷ~ㅋㄹㅋ[CREATE TABLE TEST(TEST VarChar(250))]
  \n    ㄷㅇㄷ~ㅋㄹㅋ[Insert into TEST(`TEST`) values('Hello1')]
  \n    ㄷㅇㄷ~ㅋㄹㅋ[Insert into TEST(`TEST`) values('Hello2')]
  \n    ㅆㅁㅆ :ㄷㅇㄷ~ㅋㄹㅋ[Select * From TEST][TEST]_\n}"/>
  <b>출력</b>
  <otl-code value="[Hello1, Hello2]"/>
  <br>실제 동작한 이미지<br>
  <img src="@/assets/image/h2print.png" alt="h2">

  <h2 class="title" id="데이터베이스_클래스">데이터베이스 클래스</h2>
  <h3 class="head" id="ㄷㅇㄷ1">?ㄷㅇㄷ?</h3><br>
  문법 : <code>:?ㄷㅇㄷ?[Driver]_ 또는 :?ㄷㅇㄷ?[Driver]&lt;공백&gt;</code>
  <p>
    출시 버전 : 2.1.0<br>
    해당 데이터베이스를 지원하는지 확인할 수 있는 기능입니다.<br>
    현재 지원하는 데이터데이스 종류<br>
    <u>H2, SQLite, PostgreSQL, MariaDB, MySQL, Oracle</u><br><br>
    <br>해당 예시는 H2 데이터베이스로 작성했습니다.
  </p>
  예시<otl-code value="ㅆㅁㅆ :?ㄷㅇㄷ?[org.h2.Driver]_"/>
  출력<otl-code value="ㅇㅇ"/><br>

  <h3 class="head" id="ㄷㅇㄷ6">ㄷㅇㄷ[][][][][][]</h3><br>
  문법 : <code>ㄷㅇㄷ[종류][IP][포트][데이터베이스 이름][유저이름][비밀번호]</code>
  <p>
    출시 버전 : 2.1.0<br>
    데이터베이스 클래스를 정의하는 첫번째 방법입니다.<br>
  </p>
  예시<otl-code value="ㄷㅇㄷ[종류][ip][port][dbName][user][password]"/>
  출력<otl-code value=""/>
  <br>

  <h3 class="head" id="ㄷㅇㄷ3">ㄷㅇㄷ[][][]</h3><br>
  문법 : <code>ㄷㅇㄷ[url][user][password]</code>
  <p>
    출시 버전 : 2.1.0<br>
    데이터베이스 클래스를 정의하는 두번째 방법입니다.<br>
  </p>
  예시<otl-code value="ㄷㅇㄷ[jdbc:h2:tcp://localhost/~/test][sa][ ]"/>
  출력<otl-code value=""/><br>

  <h2 class="title" id="데이터베이스_메소드">데이터베이스 메소드</h2>
  <h3 class="head" id="ㅋㄹㅋ1">ㄷㅇㄷ~ㅋㄹㅋ[]</h3><br>
  문법 : <code>ㄷㅇㄷ~ㅋㄹㅋ[SQL]</code>
  <p>
    출시 버전 : 2.1.0<br>
    SQL를 실행시키는 문법 입니다.<br>
  </p>
  예시<otl-code value="ㄷㅇㄷ~ㅋㄹㅋ[Insert into TEST(`TEST`) values('Hello')]"/>
  출력<otl-code value=""/><br>

  <h3 class="head" id="ㅋㄹㅋ2">ㄷㅇㄷ~ㅋㄹㅋ[][]</h3><br>
  문법 : <code>:ㄷㅇㄷ~ㅋㄹㅋ[SQL][value](_또는[공백])</code>
  <p>
    출시 버전 : 2.1.0<br>
    SELECT는 반환 타입이 존재하기 때문에 따로 메소드가 존재합니다.<br>
    SQL문을 쓰고 value에 컬럼명을 쓰면 배열로 해당하는 값이 출력됩니다.<br>
  </p>
  예시<otl-code value="ㅆㅁㅆ :ㄷㅇㄷ~ㅋㄹㅋ[Select * From TEST][TEST]_"/>
  출력<otl-code value="[Hello, Hello]"/><br>
</template>

<script>
import OtlCode from "@/components/edit/otl-code";

export default {
  name: "poi-database",
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