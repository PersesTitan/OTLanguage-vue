<template>
  <h1 style="padding-top: 20px">Github 기술 배지</h1>
  <div v-for="item in items" :key="item.id">
    <otl-hr>{{ item.name }}</otl-hr>
    <img v-bind:src="item.image" alt="{{ item.name }}" style="margin-bottom: 25px;"/>
    <br><b>HTML</b>
    <otl-code style="width: 70%; margin: auto">&lt;img src="{{ item.banner }}"/&gt;</otl-code>
    <br><b>MarkDown</b>
    <otl-code style="width: 70%; margin: auto">![]({{ item.banner }})</otl-code>
    <br>
  </div>
</template>

<script>
import OtlCode from '@/components/edit/otl-code';
import OtlHr from "@/components/edit/otl-hr";


export default {
  name: "music-summary",
  components: {
    OtlHr,
    OtlCode
  },
  data() {
    return {
      items: [
        {
          name: "flat",
          banner: "https://github.com/OTLanguage/.github/blob/main/icon/music/OTLanguageMusic-flat.svg",
          image: require("../../assets/github/music/OTLanguageMusic-flat.svg")
        },
        {
          name: "flat-square",
          banner: "https://github.com/OTLanguage/.github/blob/main/icon/music/OTLanguageMusic-flat-square.svg",
          image: require("../../assets/github/music/OTLanguageMusic-flat-square.svg")
        },
        {
          name: "for-the-badge",
          banner: "https://github.com/OTLanguage/.github/blob/main/icon/music/OTLanguageMusic-for-the-badge.svg",
          image: require("../../assets/github/music/OTLanguageMusic-for-the-badge.svg")
        },
        {
          name: "plastic",
          banner: "https://github.com/OTLanguage/.github/blob/main/icon/music/OTLanguageMusic-plastic.svg",
          image: require("../../assets/github/music/OTLanguageMusic-plastic.svg")
        },
        {
          name: "social",
          banner: "https://github.com/OTLanguage/.github/blob/main/icon/music/OTLanguageMusic-social.svg",
          image: require("../../assets/github/music/OTLanguageMusic-social.svg")
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>