<template>
  <h1 style="margin-top: 100px">정보</h1>
  <div style="padding: 20px"/>
  <p>
    개발 : OTLanguage<br/>
    종류 : 난해한 프로그래밍 언어<br/>
    창시자 : PersesTitan<br/>
    협력자 : - <br/>
    공식 Github Link : https://github.com/OTLanguage<br/>
    공식 블로그 Link : https://velog.io/@persestitan/series/OTLanguage
  </p>
  <div style="padding: 50px"/>
  <a class="icon" href="https://github.com/OTLanguage">
    <div style="margin: auto">
      <svg width="15%" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <title>GitHub</title>
        <path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/>
      </svg>
      <div style="vertical-align: middle;"><b>&nbsp;Github</b></div>
    </div>
  </a>
  <a class="icon" href="https://velog.io/@persestitan/series/OTLanguage">
    <div style="margin: auto;">
      <svg width="15%" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <title>Velog</title>
        <path d="M3 0C1.338 0 0 1.338 0 3v18c0 1.662 1.338 3 3 3h18c1.662 0 3-1.338 3-3V3c0-1.662-1.338-3-3-3H3Zm6.883 6.25c.63 0 1.005.3 1.125.9l1.463 8.303c.465-.615.846-1.133 1.146-1.553.465-.66.893-1.418 1.283-2.273.405-.855.608-1.62.608-2.295 0-.405-.113-.727-.338-.967-.21-.255-.608-.577-1.193-.967.6-.765 1.35-1.148 2.25-1.148.48 0 .878.143 1.193.428.33.285.494.704.494 1.26 0 .93-.39 2.093-1.17 3.488-.765 1.38-2.241 3.457-4.431 6.232l-2.227.156-1.711-9.628h-2.25V7.24c.6-.195 1.305-.406 2.115-.63.81-.24 1.358-.36 1.643-.36Z"/>
      </svg>
      <div style="vertical-align: middle"><b>&nbsp;Velog</b></div>
    </div>
  </a>
</template>

<script>
export default {
  name: "otl-information",
}
</script>

<style scoped>
a.icon {
  fill: black;
  display: inline-flex;
  align-items: center;
  padding: 0;
  font-size: large;
  color: black;
}

a.icon:hover > div > svg {
  fill: mediumpurple;
}

a.icon:hover {
  color: mediumpurple;
}
</style>