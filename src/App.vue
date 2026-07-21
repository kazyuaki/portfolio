<script setup lang="ts">
</script>

<template>
  <div class="app">
    <header class="header">
      <div class="header__inner">
        <a href="#" class="logo">Kazuaki Portfolio</a>

        <nav class="nav">
          <a href="#about">About</a>
          <a href="#skills">Skills</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </nav>
      </div>
    </header>

    <main>
      <section class="hero">
        <p class="hero__label">Web Application Engineer</p>
        <h1>山本 和明</h1>
        <p class="hero__description">
          Laravel・Vue・Nuxtを中心に、Webアプリケーションを開発しています。
        </p>

        <div class="hero__actions">
          <a href="#projects" class="button button--primary">
            制作物を見る
          </a>

          <a
            href="https://github.com/kazyuaki"
            target="_blank"
            rel="noopener noreferrer"
            class="button button--secondary"
          >
            GitHub
          </a>
        </div>
      </section>

      <section id="about" class="section">
        <h2>About</h2>
        <p>自己紹介をここに記載します。</p>
      </section>

      <section id="skills" class="section">
        <h2>Skills</h2>
        <p>技術スタックをここに記載します。</p>
      </section>

      <section id="projects" class="section">
        <h2>Projects</h2>
        <p>制作物をここに掲載します。</p>
      </section>

      <section id="contact" class="section">
        <h2>Contact</h2>
        <p>GitHubなどの連絡先を掲載します。</p>
      </section>
    </main>
  </div>
</template>