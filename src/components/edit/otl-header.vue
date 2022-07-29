<template>
  <header class="header-top">
    <a href="/" style="z-index: 100">
      <img :src="require(`@/assets/banner/${ path }-banner.png`)" :alt="path">
    </a>
    <ul class="menu">
      <li>
        <a v-bind:href="music_link">Music</a>
        <ul class="submenu">
          <li><a v-bind:href="music_link + int">소개</a></li>
          <li><a v-bind:href="music_link + sum">개요</a></li>
          <li><a v-bind:href="music_link + dow">다운로드</a></li>
          <li><a v-bind:href="music_link + gra">문법</a></li>
          <li><a v-bind:href="music_link + inf">정보</a></li>
        </ul>
      </li>
      <li>
        <a v-bind:href="poison_link">Poison</a>
        <ul class="submenu">
          <li><a v-bind:href="poison_link + int">소개</a></li>
          <li><a v-bind:href="poison_link + sum">개요</a></li>
          <li><a v-bind:href="poison_link + dow">다운로드</a></li>
          <li><a v-bind:href="poison_link + gra">문법</a></li>
          <li><a v-bind:href="poison_link + inf">정보</a></li>
        </ul>
      </li>
      <li>
        <a v-bind:href="otl_link">OTLanguage</a>
        <ul class="submenu">
          <li><a v-bind:href="otl_link + int">소개</a></li>
          <li><a v-bind:href="otl_link + sum">개요</a></li>
          <li><a v-bind:href="otl_link + dow">다운로드</a></li>
          <li><a v-bind:href="otl_link + gra">문법</a></li>
          <li><a v-bind:href="otl_link + inf">정보</a></li>
        </ul>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "otl-header",
  data() {
    return {
      link: "/",
      otl_link : "/OTLanguage",
      music_link : "/Music",
      poison_link : "/Poison",
      int: "/introduce",
      sum: "/summary",
      dow: "/download",
      gra: "/grammar",
      inf: "/information",
      kind : "OTLanguage",
      path : window.location.pathname.split('/')[1], // OTLanguage, Poison, Music, ...
      subLink : window.location.pathname.split('/')[2] //download, subtotal, ...
    }
  }
}
</script>

<style scoped>

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
  background-color: #b223ff;
}

.submenu {
  height: 0;
  overflow: hidden;
}

.menu > li:hover {
  background-color: #b223ff;
  transition-duration: 0.5s;
}

.menu > li:hover .submenu {
  height: 250px; /*서브메뉴 li한개의 높이 50*5*/
  transition-duration: 1s;
}
</style>