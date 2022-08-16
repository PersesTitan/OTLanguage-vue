<template>
  <div v-if="path === ''">
    <otl-main/>
  </div>
  <div v-else>
    <header>
      <otl-header/>
    </header>
    <div style="margin-top: 70px">
      <div v-if="path === 'Music'">
        <music-information v-if="subLink === 'information'"/> <!-- 정보 페이지 -->
        <otl-grammar v-else-if="subLink === 'grammar'"/> <!-- 문법 페이지 -->
        <v-download v-else-if="subLink === 'download'"/> <!-- 다운로드 페이지 -->
        <music-summary v-else-if="subLink === 'github'"/> <!-- 깃허브 -->
      </div>

      <div v-else-if="path === 'Poison'">
        <poison-information v-if="subLink === 'information'"/> <!-- 정보 페이지 -->
        <v-download v-else-if="subLink === 'download'"/> <!-- 다운로드 페이지 -->
        <poison-summary v-else-if="subLink === 'github'"/> <!-- 깃허브 -->
        <otl-grammar v-else-if="subLink === 'grammar'"/> <!-- 문법 페이지 -->
        <poison-introduce v-else/> <!-- 소계 페이지 -->
      </div>

      <div v-else>
        <otl-grammar v-if="subLink === 'grammar'"/> <!-- 문법 페이지 -->
        <v-download v-else-if="subLink === 'download'"/> <!-- 다운로드 페이지 -->
        <otl-information v-else-if="subLink === 'information'"/> <!-- 정보페이지 -->
        <otl-summary v-else-if="subLink === 'github'"/> <!-- 깃허브 -->
        <otl-introduce v-else/> <!-- 소계 페이지 -->
      </div>
    </div>
  </div>
  
</template>

<script>

// const mainColor = "#A900FF"
import VDownload from "@/components/v-download";
import OtlMain from "@/components/otl-main";
import OtlHeader from "@/components/edit/otl-header"
import OtlGrammar from "@/components/otl/otl-grammar";
import OtlIntroduce from "@/components/otl/otl-introduce";
import OtlInformation from "@/components/otl/otl-information";
import PoisonInformation from "@/components/poison/poison-information";
import MusicInformation from "@/components/music/music-information";
import OtlSummary from "@/components/otl/otl-summary";
import PoisonSummary from "@/components/poison/poison-summary";
import MusicSummary from "@/components/music/music-summary";
import PoisonIntroduce from "@/components/poison/poison-introduce";

export default {
  name: 'App',
  components: {
    PoisonIntroduce,
    MusicSummary,
    PoisonSummary,
    OtlSummary,
    MusicInformation,
    PoisonInformation,
    OtlInformation,
    OtlIntroduce,
    OtlGrammar,
    OtlMain,
    VDownload,
    OtlHeader
  },
  data() {
    return {
      otl_link : "/OTLanguage",
      music_link : "/Music",
      poison_link : "/Poison",
      kind : "OTLanguage",
      path : window.location.pathname.split('/')[1], // OTLanguage, Poison, Music, ...
      subLink : window.location.pathname.split('/')[2] //download, subtotal, ...
    }
  }
}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.submenu li {
  font-weight: normal;
}

.submenu > li:hover {
  background: #a200ff;
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
