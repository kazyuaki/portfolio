<script setup lang="ts">
import { ArrowUpRight, Github } from "lucide-vue-next";

const currentYear = new Date().getFullYear();
</script>

<template>
  <section id="contact" class="contact" aria-labelledby="contact-title">
    <div class="contact__glow contact__glow--left" aria-hidden="true"></div>
    <div class="contact__glow contact__glow--right" aria-hidden="true"></div>

    <div class="contact__inner">
      <div class="contact__content">
        <p class="contact__eyebrow">Contact</p>
        <h2 id="contact-title">ここまでご覧いただき、<br />ありがとうございます。</h2>
        <p class="contact__description">
          制作物やこれまでの取り組みに興味を持っていただけましたら、
          GitHubからぜひご覧ください。
        </p>

        <a
          href="https://github.com/kazyuaki"
          target="_blank"
          rel="noopener noreferrer"
          class="contact__button"
        >
          <Github :size="20" aria-hidden="true" />
          GitHubを見る
          <ArrowUpRight :size="18" aria-hidden="true" />
        </a>
      </div>

      <footer class="contact__footer">
        <a href="#top" class="contact__name">Kazuaki Yamamoto</a>

        <nav aria-label="フッターナビゲーション">
          <a href="#about">About</a>
          <a href="#skills">Skills</a>
          <a href="#projects">Projects</a>
        </nav>

        <p>© {{ currentYear }} Kazuaki Yamamoto</p>
      </footer>
    </div>
  </section>
</template>

<style scoped>
.contact {
  position: relative;
  padding: 128px 24px 32px;
  overflow: hidden;
  scroll-margin-top: 104px;
  color: #fff;
  background: #0f172a;
}

.contact::before {
  position: absolute;
  inset: 0;
  content: "";
  opacity: 0.2;
  background-image:
    linear-gradient(rgba(148, 163, 184, 0.08) 1px, transparent 1px),
    linear-gradient(90deg, rgba(148, 163, 184, 0.08) 1px, transparent 1px);
  background-size: 48px 48px;
  mask-image: linear-gradient(to bottom, #000, transparent 78%);
}

.contact__glow {
  position: absolute;
  border-radius: 50%;
  pointer-events: none;
  filter: blur(110px);
}

.contact__glow--left {
  top: 15%;
  left: -150px;
  width: 380px;
  height: 380px;
  background: rgba(37, 99, 235, 0.3);
}

.contact__glow--right {
  right: -170px;
  bottom: -160px;
  width: 420px;
  height: 420px;
  background: rgba(59, 130, 246, 0.2);
}

.contact__inner {
  position: relative;
  width: min(1120px, 100%);
  margin: 0 auto;
}

.contact__content {
  max-width: 780px;
  padding-bottom: 112px;
}

.contact__eyebrow {
  margin: 0 0 20px;
  color: #60a5fa;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.contact h2 {
  margin: 0;
  font-size: clamp(38px, 5.5vw, 68px);
  font-weight: 600;
  letter-spacing: -0.04em;
  line-height: 1.35;
}

.contact__description {
  max-width: 650px;
  margin: 28px 0 0;
  color: #94a3b8;
  font-size: 17px;
  line-height: 1.9;
}

.contact__button {
  display: inline-flex;
  gap: 10px;
  align-items: center;
  margin-top: 42px;
  padding: 15px 24px;
  border: 1px solid rgba(255, 255, 255, 0.16);
  border-radius: 999px;
  color: #0f172a;
  font-size: 14px;
  font-weight: 700;
  text-decoration: none;
  background: #fff;
  box-shadow: 0 16px 36px rgba(0, 0, 0, 0.22);
  transition:
    box-shadow 0.2s ease,
    transform 0.2s ease;
}

.contact__button:hover {
  box-shadow: 0 20px 42px rgba(37, 99, 235, 0.28);
  transform: translateY(-3px);
}

.contact__button:focus-visible,
.contact__footer a:focus-visible {
  outline: 3px solid #60a5fa;
  outline-offset: 4px;
}

.contact__footer {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 32px;
  align-items: center;
  padding-top: 28px;
  border-top: 1px solid rgba(148, 163, 184, 0.18);
}

.contact__name {
  justify-self: start;
  color: #fff;
  font-size: 14px;
  font-weight: 700;
  text-decoration: none;
}

.contact__footer nav {
  display: flex;
  gap: 24px;
}

.contact__footer nav a,
.contact__footer p {
  color: #64748b;
  font-size: 12px;
  font-weight: 600;
  text-decoration: none;
}

.contact__footer nav a {
  transition: color 0.2s ease;
}

.contact__footer nav a:hover {
  color: #fff;
}

.contact__footer p {
  justify-self: end;
  margin: 0;
}

@media (max-width: 760px) {
  .contact {
    padding: 96px 20px 28px;
  }

  .contact__content {
    padding-bottom: 80px;
  }

  .contact h2 {
    font-size: 38px;
  }

  .contact__description {
    font-size: 15px;
  }

  .contact__footer {
    grid-template-columns: 1fr;
    gap: 20px;
  }

  .contact__name,
  .contact__footer p {
    justify-self: start;
  }

  .contact__footer nav {
    gap: 20px;
    flex-wrap: wrap;
  }
}

@media (prefers-reduced-motion: reduce) {
  .contact__button {
    transition: none;
  }
}
</style>
