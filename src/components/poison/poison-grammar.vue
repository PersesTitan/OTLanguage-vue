<template>
  <div v-if="more === 'undefined'">
    <ul class="menu" style="padding-top: 50px">
      <li><a v-bind:href="link + allVariable">All</a></li>
      <li><a v-bind:href="link + consoleVariable">콘솔</a></li>
      <li><a v-bind:href="link + normalVariable">변수</a></li>
      <li><a v-bind:href="link + listVariable">리스트</a></li>
      <li><a v-bind:href="link + singVariable">기호</a></li>
    </ul>
    <br>

  </div>
  <div v-else>

  </div>
</template>

<script>
const list = []

export default {
  name: "poison-grammar",
  data() {
    return {
      kind: window.location.pathname.split('/')[3], //console, normal, ...
      more: decodeURIComponent(window.location.pathname.split('/')[4]),
      link: "/Poison/grammar/",
      consoleVariable: "console",
      normalVariable: "normal",
      listVariable: "list",
      singVariable: "sing",
      allVariable: "all",
      all: this.addAll(),
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