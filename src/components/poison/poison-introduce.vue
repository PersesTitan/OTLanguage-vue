<template>
  <h1 style="margin-top: 100px">소개</h1>
  <otl-hr>Poison</otl-hr>

  <div class="otl-int">
    <h3>&bull;&nbsp;&nbsp;Poison</h3>
    <div class="content">
      <p>
        <b>- 간단한 소개</b><br>
        Poison은 OTLanguage로 구현하는 백앤드 웹프레임워크 입니다.<br>
        난해한언어로 구현할 수 있는 최초 백앤드 웹 프레임워크 입니다.<br>
        <b>- 이름 유래</b><br>
        영어로 독을 의미하는 Poison이 되었습니다.
      </p>
    </div>
    <br>

    <h3>&bull;&nbsp;&nbsp;접근</h3>
    <div class="content">
      <p>
        해당 프레임워크는 실전 적용이 어려울 수 있기때문에 간단한 <u>취미 및 난해한 언어 학습</u> 목표로 해보시는 걸 추천 드립니다. <br>
        Poison은 간단한 웹사이트 구현등에 추천합니다.
      </p>
    </div>
    <br>

    <h3>&bull;&nbsp;&nbsp;기본 포트 번호</h3>
    <div class="content">
      <p>
        Poison의 기본 포트는 <b>9090</b>입니다.<br>
        포트는 코드를 통해 변경이 가능합니다.
      </p>
    </div>
    <br>

    <h3>&bull;&nbsp;&nbsp;데이터베이스</h3>
    <div class="content">
      <p>
        <b>현재 지원하고 있는 데이터베이스</b><br>
        (모든 데이터베이스를 확인하지 못하였기 때문에 일부 데이터베이스는 재대로 작동하지 않을 수 있습니다.)<br>
        <u>SQLite, H2, PostgreSQL, MariaDB, MySQL, Oracle, Tomcat, Hive</u>
      </p>
      <b>지원하는 데이터베이스인지 확인하는 법</b><br>
      드라이브를 이용해 해당 디비가 지원하는 디비인지 확인이 가능합니다.<br>
      ?ㄷㅇㄷ?[Driver]이라는 문법을 이용하면 지원을 하는 드라이브라면 ㅇㅇ을 지원하지 않으면 ㄴㄴ를 반환해줍니다.<br>
      <br>
      해당 예제는 지원을 하는 데이터베이스라면 <u>"지원하는 데이터베이스 입니다."</u>라고 출력하게 되는 코드 입니다.
      <otl-code value="?ㅅ? :?ㄷㅇㄷ?[Driver]_ { <br>&nbsp;&nbsp;&nbsp;ㅆㅁㅆ 지원하는 데이터베이스 입니다.<br> }"/>
    </div>
    <br>

  </div>
</template>

<script>
import OtlHr from "@/components/edit/otl-hr";
import OtlCode from "@/components/edit/otl-code";

export default {
  name: "poison-introduce",
  components: {
    OtlCode,
    OtlHr
  }
}
</script>

<style scoped>
/*기본 스타일*/
div.moveKind {
  display: inline;
  border-radius: 50px;
  padding: 5px 10px;
  color: black;
  background-color: #ce80ff;
}

div.moveKind:hover {
  color: white;
  background-color: #A900FF;
}

/*링크 스타일*/
div.moveKind > a {
  color: black;
}

div.moveKind:hover > a {
  color: white;
}

div.content {
  width: 95%;
  margin: auto;
}

div.otl-int {
  text-align: left;
  margin: auto;
  width: 80%;
}
</style>