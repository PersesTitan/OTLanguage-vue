<template>
  <h1 style="margin-top: 100px">소개</h1>
  <otl-hr>OTLanguage</otl-hr>

  <div class="otl-int">
    <h3>&bull;&nbsp;&nbsp;OTLanguage</h3>
    <div class="content">
      <p>
        <b>- 간단한 소개</b><br>
        OTLanguage는 주로 이모티콘으로 이루어진 난해한 프로그래밍 언어 입니다.<br>
        <b>- 이름 유래</b><br>
        절망하는 이모티콘인 OTL과 언어를 의미하는 Language를 합쳐서 OTLanguage가 되었습니다.
      </p>
    </div>
    <br>

    <h3>&bull;&nbsp;&nbsp;동작방식</h3>
    <div class="content">
      <p>
        OTLanguage는 1줄씩 코드를 위에서 부터 순서대로 읽어가면서 동작하는 방식으로 동작을 하는 인터프린터 언어 입니다.<br>
        분석할때 주로 줄바꿈이나 공백(탭, 스페이스바 등)을 기준으로 분리하기 때문에 코드를 작성하실때 주의하여주세요.
      </p>
      <div v-on:click="scroll('#moveKind')" class="moveKind">
        동작 방식 표 바로가기
      </div>
    </div>
    <br><br>

    <h3>&bull;&nbsp;&nbsp;OTLanguage는 Java기반 언어 입니다.</h3>
    <div class="content">
      <p>
        분석기가 <b>Java</b>기반으로 구현이 되어 있기때문에 동작하기 때문에 컴퓨터에 <b>Java</b>
        가 설치 되어 있어야 정상적으로 동작을 합니다. (권장 버전 : 17) <br/>
      </p>
      <div class="moveKind">
        <a href="https://www.oracle.com/java/technologies/downloads/">Java</a>
      </div>
    </div>
    <br/><br/>

    <h3>&bull;&nbsp;&nbsp;파일 확장자</h3>
    <div class="content">
      <p>파일 확장자는 <b>.otl</b>를 사용합니다.</p>
    </div>
    <br/>

    <h3>&bull;&nbsp;&nbsp;OTLanguage는 기본 타입이 문자열입니다.</h3>
    <div class="content">
      <p>기본 타입이 문자열이므로 큰 따옴표(")나 작은 따옴표(')를 사용하지 않습니다.</p>
      <div style="font-weight: bold">otl</div>
      <otl-code value='ㅆㅁㅆ "Hello World"<br>ㅆㅁㅆ Hello World'/>
<!--      <otl-code>-->
<!--        <otl-p>ㅆㅁㅆ</otl-p> "Hello World"<br>-->
<!--        <otl-p>ㅆㅁㅆ</otl-p> Hello World-->
<!--      </otl-code>-->
      <div style="font-weight: bold">출력</div>
      <otl-code>
        "Hello World"<br>
        Hello World
      </otl-code>
      <br>
      <p>
        문자열을 기본값으로 가져오기 때문에 변수에 동작을 넣고 변수값을 가져오는 것만으로 해당 동작을 사용할 수 있습니다.<br>
        <br><b>아래 예시 코드 분석</b><br>
        1. a:&lt;&lt;test라는 값을 가지고 있는 문자형 변수 list 생성<br>
        2. 리스트 변수 a 생성<br>
        3. list변수로 부터 값을 꺼내옴 (:list_ = a:&lt;&lt;test)<br>
        (list 변수에 a:&lt;&lt;test라는 값이 담겨져 있기때문에 변수를 꺼내오는 것으로 a:&lt;&lt;test과 같은 동작을 수행하게 됩니다.)<br>
        4. list 값 출력
      </p>
      <div style="font-weight: bold">otl</div>
      <otl-code>
        <otl-o>ㅇㅁㅇ</otl-o> list:a:&lt;&lt;test<br/>
        <otl-o>ㄹㅁㄹ</otl-o> a<br/>
        :list_<br/>
        :list_<br/>
        :list_<br/>
        <otl-p>ㅆㅁㅆ</otl-p> :a_
      </otl-code>
      <div style="font-weight: bold">출력</div>
      <otl-code>
        [test, test, test]
      </otl-code>
      <br/>
    </div>

    <h3 id="moveKind">&bull;&nbsp;&nbsp;동작 방식</h3>
    <div class="content">
      <fieldset style="text-align: center">
        <legend style="padding-left: 10px; padding-right: 10px; text-align: left">동작 구조</legend>
        <img src="../../assets/svg/movement-OTL.svg" alt="movement" style="width: 100%; margin: auto">
      </fieldset>
      <br/>
    </div>

  </div>
</template>

<script>
import OtlHr from "@/components/edit/otl-hr";
import OtlCode from "@/components/edit/otl-code";
import OtlP from "@/components/code-color/otl-p";
import OtlO from "@/components/code-color/otl-o";

export default {
  name: "otl-introduce",
  components: {
    OtlP, OtlO,
    OtlHr, OtlCode
  },
  methods: {
    scroll(id) {
      const height = document.querySelector(id).offsetHeight
      const position = document.querySelector(id).offsetTop
      window.scrollTo({top:position - height, behavior:'smooth'})
    }
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