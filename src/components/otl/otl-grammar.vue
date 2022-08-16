<template>
  <div style="position: static">
    <div class="left">
      <grammer-list/>
    </div>
    <div class="right">
      <div class="text">
        <div v-if="url === Poison">
          <poi-web v-if="kind === web"/>
          <poi-database v-else/>
        </div>
        <div v-else>
          <otl-sing v-if="kind === singVariable"/>
          <otl-variable v-else-if="kind === variableVariable"/>
          <otl-class v-else-if="kind === classVariable"/>
          <otl-console v-else/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import variable from '@/assets/json/variable.json'
import console from '@/assets/json/console.json'
import sing from '@/assets/json/sing.json'
import OtlConsole from '@/components/grammer/otl-console'
import GrammerList from "@/components/grammer/grammer-list";
import OtlVariable from "@/components/grammer/otl-variable";
import OtlClass from "@/components/grammer/otl-class";
import OtlSing from "@/components/grammer/otl-sing";
import PoiDatabase from "@/components/grammer/poi-database";
import PoiWeb from "@/components/grammer/poi-web";

const list = [variable.normal, variable.list, console, sing]

export default {
  name: "otl-grammar",
  components: {PoiWeb, PoiDatabase, OtlSing, OtlClass, OtlVariable, GrammerList, OtlConsole},
  data() {
    return {
      url: window.location.pathname.split('/')[2], //Poison, OTLanguage
      kind: window.location.pathname.split('/')[4], //console, normal, ...
      more: decodeURIComponent(window.location.pathname.split('/')[5]),
      link: "/OTLanguage/grammar/",
      OTLanguage: "OTLanguage",
      Poison: "Poison",
      Music: "Music",
      consoleVariable: "console",
      variableVariable: "variable",
      classVariable: "class",
      singVariable: "sing",
      dataBase: "datadase",
      web: "web",
      normal: variable.normal,
      list: variable.list,
      console: console,
      sing: sing,
    }
  },
  methods: {
    addAll() {
      const map = []
      list.forEach(values => values.forEach(key => map.push(key)))
      return map
    },
    updated(value) {
      const map = this.addAll()
      for (const i of map.keys()) {
        if (map[i]['name'] === value) return map[i]
      }
    }
  }
}
</script>

<style scoped>
/* 왼쪽 오른쪽 */
div.left {
  overflow: auto;
  position: fixed;
  height: 100%;
  font-size: 80%;
  width: 20%;
  background-color: red;
  float: left;
}

div.right {
  width: 80%;
  background-color: darkorange;
  float: right;
}

div.text {
  margin: auto;
  text-align: left;
  width: 95%;
}

/* 아이템 */
ul.items {
  margin: auto 30px;
  text-align: left;
}

ul.items > li {
  margin: 10px;
  list-style-type: square;
}

ul.items > li > a {
  color: black;
  border-radius: 100px;
}

ul.items > li > a:hover {
  color: rebeccapurple;
  font-weight: bolder;
}

/* 메뉴 */
div.items > div {
  display: inline-block;
}

ul.menu {
  color: white;
}

ul.menu > li {
  width: 10%;
  display: inline-grid;
  margin: 0 10px;
}

ul.menu > li > a {
  color: white;
  background-color: rebeccapurple;
  padding: 10px;
  border-radius: 5px;
}

ul.menu > li > a:hover {
  color: black;
  background-color: #ce80ff;
}
</style>