<script setup lang="ts">
import { Github } from "lucide-vue-next";
import AboutSection from "./components/AboutSection.vue";
import AppHeader from "./components/AppHeader.vue";
import SkillsSection from "./components/SkillsSection.vue";
</script>

<template>
  <AppHeader />

  <main>
    <section id="top" class="hero">
      <div class="hero__background">
        <div class="hero__blur hero__blur--1"></div>
        <div class="hero__blur hero__blur--2"></div>
        <div class="hero__blur hero__blur--3"></div>
      </div>
      <div class="hero__container">
        <span class="hero__eyebrow"> 👋 Hello, I'm </span>

        <h1 class="hero__title">山本 和明</h1>

        <p class="hero__subtitle">Web Application Engineer</p>

        <div class="hero__tech">
          <span>Laravel</span>
          <span>Vue</span>
          <span>Nuxt</span>
          <span>TypeScript</span>
          <span>Docker</span>
        </div>

        <p class="hero__description">
          Laravel・Vue・Nuxtを用いたWebアプリケーション開発を行っています。<br />
          使いやすさと保守性を大切に、企画からデプロイまで一貫して取り組んでいます。
        </p>

        <div class="hero__actions">
          <a href="#projects" class="btn btn-primary"> 制作物を見る </a>

          <a
            href="https://github.com/kazyuaki"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-secondary"
          >
            <Github :size="18" />
            GitHub
          </a>
        </div>
      </div>
      <a class="hero__scroll" href="#about">Scroll ↓</a>
    </section>

    <AboutSection />
    <SkillsSection />
  </main>
</template>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: #f8fafc;
  color: #0f172a;
  font-family: Inter, "Zen Kaku Gothic New", sans-serif;
}

.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 112px 24px 80px;
  overflow: hidden;
  background: #f8fafc;
}

.hero__background {
  position: absolute;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
}

.hero__blur {
  position: absolute;
  border-radius: 999px;
  filter: blur(140px);
  opacity: 0.55;
}

.hero__blur--1 {
  width: 520px;
  height: 520px;
  background: #93c5fd;
  top: -180px;
  left: -180px;
}

.hero__blur--2 {
  width: 420px;
  height: 420px;
  background: #60a5fa;
  right: -120px;
  bottom: -120px;
}

.hero__blur--3 {
  width: 260px;
  height: 260px;
  background: white;
  top: 120px;
  right: 30%;
  opacity: 0.9;
}

.hero__container {
  position: relative;
  z-index: 1;
  max-width: 760px;
  text-align: center;
}

.hero__eyebrow {
  display: inline-block;
  font-size: 18px;
  margin-bottom: 20px;
  color: #2563eb;
  font-weight: 600;
}

.hero__title {
  margin: 12px 0;
  font-size: clamp(64px, 8vw, 88px);
  font-family: "Noto Sans JP", sans-serif;
  font-weight: 600;
  letter-spacing: 0.04em;
  line-height: 1.05;
  color: #0f172a;
}

.hero__subtitle {
  margin-top: 18px;
  font-size: 24px;
  font-weight: 400;
  color: #475569;
}

.hero__tech {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 14px;
  margin: 40px 0;
}

.hero__tech span {
  padding: 10px 18px;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.85);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(148, 163, 184, 0.2);
  box-shadow: 0 6px 20px rgba(15, 23, 42, 0.06);
  font-weight: 600;
  transition: 0.25s;
}

.hero__tech span:hover {
  transform: translateY(-3px);
  box-shadow: 0 14px 30px rgba(37, 99, 235, 0.15);
}

.hero__description {
  margin-top: 40px;
  font-size: 18px;
  line-height: 2;
  color: #64748b;
}

.hero__actions {
  display: flex;
  justify-content: center;
  gap: 18px;
  margin-top: 52px;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 15px 32px;
  border-radius: 999px;
  font-weight: 600;
  text-decoration: none;
  transition: 0.25s;
}

.btn-primary {
  color: white;
  background: linear-gradient(135deg, #3b82f6, #2563eb);

  box-shadow: 0 15px 35px rgba(37, 99, 235, 0.25);
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 20px 40px rgba(37, 99, 235, 0.35);
}

.btn-secondary {
  color: #0f172a;
  background: rgba(255, 255, 255, 0.8);
  border: 1px solid #dbe4ef;
  backdrop-filter: blur(12px);
}

.btn-secondary:hover {
  background: white;
  transform: translateY(-3px);
}

.hero__scroll {
  position: absolute;
  bottom: 40px;
  left: 50%;
  transform: translateX(-50%);
  color: #94a3b8;
  font-size: 14px;
  letter-spacing: 0.2em;
  animation: float 2s ease-in-out infinite;
}

@keyframes float {
  0%,
  100% {
    transform: translate(-50%, 0);
  }

  50% {
    transform: translate(-50%, -8px);
  }
}

@media (max-width: 640px) {
  .hero {
    min-height: 100svh;
    padding: 104px 20px 96px;
  }

  .hero__title {
    font-size: clamp(48px, 15vw, 64px);
  }

  .hero__subtitle {
    font-size: 20px;
  }

  .hero__description {
    font-size: 16px;
    line-height: 1.9;
  }

  .hero__description br {
    display: none;
  }

  .hero__actions {
    width: 100%;
    gap: 12px;
    margin-top: 40px;
  }

  .btn {
    width: min(100%, 280px);
  }

  .hero__scroll {
    bottom: 24px;
  }
}
</style>
