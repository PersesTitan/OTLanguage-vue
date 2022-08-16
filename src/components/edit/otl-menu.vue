<template>
  <ul class="main-middle-menu">
    <li>
      <a :href="mainLink + link1">{{ item1 }}</a>
    </li>
    <li>
      <a :href="mainLink + link2">{{ item2 }}</a>
    </li>
    <li>
      <a :href="mainLink + link3">{{ item3 }}</a>
    </li>
    <li>
      <a :href="mainLink + link4">{{ item4 }}</a>
    </li>
    <li>
      <a :href="mainLink + link5">{{ item5 }}</a>
    </li>
  </ul>
</template>

<script>
export default {
  name: "otl-menu",
  props: {
    item1: {
      type: String,
      default: "소개"
    },
    item2: {
      type: String,
      default: "Github"
    },
    item3: {
      type: String,
      default: "다운로드"
    },
    item4: {
      type: String,
      default: "문법"
    },
    item5: {
      type: String,
      default: "정보"
    },
    mainLink: String,
    link1: String,
    link2: String,
    link3: String,
    link4: String,
    link5: String
  }
}
</script>

<style scoped>
ul.main-middle-menu {
}

ul.main-middle-menu > li {
  display: inline-block;
  width: 15%;
}

ul.main-middle-menu > li > a {
  background-color: white;
  color: black;
  border-radius: 30px;
  margin: 30px 5px 5px 5px;
  display: block;
  padding: 10px;
}

ul.main-middle-menu > li > a:hover {
  background-color: black;
  color: white;
}
</style>