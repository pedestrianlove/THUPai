<script setup>
// SEO settings
const title = '東海選課模擬器';
const description = '就，又一個東海選課模擬器';
const image = 'https://www.thu.edu.tw/upload/sitemap/%E6%9D%B1%E6%B5%B7%E5%A4%A7%E5%AD%B8%E4%B8%AD%E8%8B%B1%E6%96%87%E6%A0%A1%E5%90%8D%E8%A8%AD%E8%A8%88%E5%AD%97L.png';
const url = useRequestURL();
useSeoMeta({
  title,
  description,
  image,
  url,
});
</script>
<template>

  <Head>
    <title>THUwU | 東海選課模擬器</title>

  </Head>

  <Body>
    <nav class="navbar is-fixed-top" role="navigation">
      <div class="container">
        <div class="navbar-brand">
          <a class="navbar-item" href="https://cmlai-lab.github.io/THUwU/">
            <img alt="東海大學"
              src="https://www.thu.edu.tw/upload/sitemap/%E6%9D%B1%E6%B5%B7%E5%A4%A7%E5%AD%B8%E4%B8%AD%E8%8B%B1%E6%96%87%E6%A0%A1%E5%90%8D%E8%A8%AD%E8%A8%88%E5%AD%97L.png">
            選課模擬器 / 排課系統
          </a>
          <SemesterTag />
        </div>
      </div>
    </nav>
    <NuxtPage />
    <footer class="footer has-text-centered">
      <p>Designed By @splitline</p>
      <a href="https://github.com/splitline/NCTUwU" target="_blank">
        <span class="icon">
          <i class="fab fa-github"></i>
        </span>
      </a>
    </footer>
    <div class="loading is-hidden">
      <span>
        The fear of the Lord is the beginning of wisdom: and the knowledge of the holy is understanding.
      </span>
    </div>
  </Body>
</template>
