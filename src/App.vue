<template>
  <div v-if="path === ''">
    <otl-main/>
  </div>
  <div v-else>
    <header>
      <otl-header/>
    </header>
  </div>

  <div class="body">
    <div v-if="path === 'OTLanguage'">
      <otl-grammar v-if="subLink === 'grammar'"/>
      <v-download v-else-if="subLink === 'download'"/>
      <otl-information v-else-if="subLink === 'information'"/>
      <otl-introduce v-else/>
    </div>
    <div v-else-if="path === 'Poison'">
      <poison-information v-if="subLink === 'information'"/>
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

export default {
  name: 'App',
  components: {
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
  },
  // updated() {
  //   const ele = document.getElementsByTagName('body')
  //   const app = document.getElementById('app')
  //   if (this.path === '') {
  //     ele.style.marginTop = 0
  //     ele.style.margin = 0
  //     app.style.marginTop = 0
  //   } else {
  //     ele.style.marginTop = 70
  //     app.style.marginTop = 60
  //   }
  // }

  updated() {
    const app = document.getElementById('app')
    if (this.path === '') {
      app.style.marginTop = "0px"
    } else {
      app.style.marginTop = "60px"
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
  /*margin-top: 70px;*/
}

div.body {
  /*margin-top: 70px;*/
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
