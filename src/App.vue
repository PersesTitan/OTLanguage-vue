<template>
  <div v-if="path === ''">
    <otl-main/>
  </div>

  <div v-else>
    <header class="header-top">
      <img :src="require(`@/assets/banner/${ path }-banner.png`)" alt="/{{ path }}">
      <ul class="menu">
        <li>
          <a href="/Music">Music</a>
          <ul class="submenu">
            <li><a>개요</a></li>
            <li><a>다운로드</a></li>
          </ul>
        </li>
        <li>
          <a href="/Poison">Poison</a>
          <ul class="submenu">
            <li><a>개요</a></li>
            <li><a>다운로드</a></li>
          </ul>
        </li>
        <li>
          <a href="/OTLanguage">OTLanguage</a>
          <ul class="submenu">
            <li><a href="/OTLanguage">소개</a></li>
            <li><a href="/OTLanguage">개요</a></li>
            <li><a href="/OTLanguage/download">다운로드</a></li>
            <li><a href="/OTLanguage">문법</a></li>
            <li><a href="/OTLanguage">정보</a></li>
          </ul>
        </li>
      </ul>
    </header>
  </div>

  <div v-if="subLink === 'download'">
    <v-download/>
  </div>

  <otl-code>
    <otl-p>ㅅㅁㅅ</otl-p>&nbsp;안녕하세요.
  </otl-code>

</template>

<script>

// const mainColor = "#A900FF"
import VDownload from "@/components/v-download";
import OtlCode from "@/components/edit/otl-code";
import OtlP from "@/components/code-color/otl-p"
import OtlMain from "@/components/otl-main";

export default {
  name: 'App',
  components: {
    OtlMain,
    OtlP,
    OtlCode,
    VDownload
  },
  data() {
    return {
      otl_link : "/OTLanguage",
      music_link : "/Music",
      poison_link : "/Poison",
      kind : "OTLanguage",
      path : window.location.pathname.split('/')[1],
      subLink : window.location.pathname.split('/')[2] //download, subtotal, ...
    }
  },
  updated() {
    const ele = document.getElementsByTagName('body')
    if (this.path === '') ele.style.marginTop = '0px'
    else ele.style.marginTop = '70px'
  }
}
</script>

<style>
body {
  margin: 0;
}

/*배너 정의*/
.header-top {
  position: fixed;
  display: flex;
  left: 0;
  right: 0;
  top: 0;
  justify-content: space-between;
  align-items: center;
  background: #ce80ff;
  height: 70px;
}

.header-top img {
  margin-left: 10px;
  height: 70px;
  left: 0;
  top: 0;
}

/*메뉴*/
.menu {
  position: fixed;
  left: 0;
  top: 0;
  overflow: hidden;
  width: 100%;
  margin: 0;
}

.menu > li {
  width: 20%; /*20*5=100%*/
  /*float: right;*/
  display: inline-grid;
  float: right;
  text-align: center;
  /*margin-top: 15px;*/
  line-height: 70px;
  font-weight: bold;
  background-color: #00000000;
}

.menu a {
  color: black;
  display: block;
}

.submenu > li {
  line-height: 50px;
  background-color: purple;
}

.submenu {
  height: 0;
  overflow: hidden;
}

.menu > li:hover {
  background-color: purple;
  transition-duration: 0.5s;
}

.menu > li:hover .submenu {
  height: 250px; /*서브메뉴 li한개의 높이 50*5*/
  transition-duration: 1s;
}

.submenu li {
  font-weight: normal;
}

.submenu > li:hover {
  background: blue;
  color: white;
}

.menu a:hover {
  color: white;
}

ul {
  padding-left: 0;
  text-align: center;
  list-style: none;
}

a {
  text-decoration-line: none;
}
</style>
