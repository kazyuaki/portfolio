<script setup lang="ts">
import { ExternalLink, Github } from "lucide-vue-next";
import { ref } from "vue";
import taskFlowImage from "../assets/projects/task-flow.png";
import taskFlowDetailImage from "../assets/projects/task-flow-detail.png";
import taskFlowProfileImage from "../assets/projects/task-flow-profile.png";

const screenshots = [
  {
    src: taskFlowImage,
    label: "タスク一覧",
    alt: "Task Flowのタスク一覧画面",
  },
  {
    src: taskFlowDetailImage,
    label: "タスク詳細",
    alt: "Task Flowのタスク詳細画面",
  },
  {
    src: taskFlowProfileImage,
    label: "プロフィール",
    alt: "Task Flowのプロフィール画面",
  },
];

const activeScreenshot = ref(0);

const technologies = [
  "Laravel",
  "Nuxt",
  "TypeScript",
  "MySQL",
  "Docker",
  "Nginx",
];
</script>

<template>
  <section id="projects" class="projects" aria-labelledby="projects-title">
    <div class="projects__inner">
      <header class="projects__heading">
        <p class="projects__eyebrow">Projects</p>
        <h2 id="projects-title">課題から考え、<br />公開まで仕上げた制作物。</h2>
        <p>
          設計・実装だけでなく、使いやすさや運用も意識して開発した
          Webアプリケーションを紹介します。
        </p>
      </header>

      <article class="project-card">
        <div class="project-card__visual">
          <div class="project-gallery">
            <img
              :src="screenshots[activeScreenshot].src"
              :alt="screenshots[activeScreenshot].alt"
              class="project-card__image"
            />

            <div class="project-gallery__thumbnails" aria-label="画面を切り替える">
              <button
                v-for="(screenshot, index) in screenshots"
                :key="screenshot.label"
                type="button"
                :class="['project-gallery__thumbnail', { 'is-active': activeScreenshot === index }]"
                :aria-pressed="activeScreenshot === index"
                @click="activeScreenshot = index"
              >
                <img :src="screenshot.src" alt="" />
                <span>{{ screenshot.label }}</span>
              </button>
            </div>
          </div>
        </div>

        <div class="project-card__content">
          <div class="project-card__meta">
            <span>Featured Project</span>
            <small>01</small>
          </div>

          <h3>Task Flow</h3>
          <p class="project-card__lead">
            日々のタスクを、迷わず整理・管理できるタスク管理アプリ。
          </p>
          <p class="project-card__description">
            認証、タスクCRUD、カテゴリ管理、絞り込み、プロフィール編集などを実装。
            NuxtとLaravelを分離した構成で開発し、Docker環境からVPSへの公開まで
            一貫して取り組みました。
          </p>

          <ul class="project-card__tech" aria-label="Task Flowの使用技術">
            <li v-for="technology in technologies" :key="technology">
              {{ technology }}
            </li>
          </ul>

          <div class="project-card__actions">
            <a
              href="https://taskflow-app-kazu.com"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link project-link--primary"
            >
              <ExternalLink :size="18" />
              アプリを見る
            </a>
            <a
              href="https://github.com/kazyuaki/task-flow-app-by-vue"
              target="_blank"
              rel="noopener noreferrer"
              class="project-link project-link--secondary"
            >
              <Github :size="18" />
              GitHub
            </a>
          </div>
        </div>
      </article>
    </div>
  </section>
</template>

<style scoped>
.projects {
  position: relative;
  padding: 128px 24px;
  overflow: hidden;
  scroll-margin-top: 104px;
  background: #f1f5f9;
}

.projects::before {
  position: absolute;
  top: -180px;
  right: -140px;
  width: 480px;
  height: 480px;
  border-radius: 50%;
  content: "";
  background: rgba(96, 165, 250, 0.18);
  filter: blur(120px);
}

.projects__inner {
  position: relative;
  width: min(1120px, 100%);
  margin: 0 auto;
}

.projects__heading {
  max-width: 710px;
  margin-bottom: 56px;
}

.projects__eyebrow {
  margin: 0 0 18px;
  color: #2563eb;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.projects__heading h2 {
  margin: 0;
  color: #0f172a;
  font-size: clamp(36px, 4.5vw, 56px);
  font-weight: 600;
  letter-spacing: -0.035em;
  line-height: 1.35;
}

.projects__heading > p:last-child {
  margin: 24px 0 0;
  color: #64748b;
  font-size: 17px;
  line-height: 1.9;
}

.project-card {
  display: grid;
  grid-template-columns: minmax(0, 1.15fr) minmax(360px, 0.85fr);
  overflow: hidden;
  border: 1px solid rgba(148, 163, 184, 0.22);
  border-radius: 30px;
  background: rgba(255, 255, 255, 0.9);
  box-shadow: 0 28px 70px rgba(15, 23, 42, 0.1);
}

.project-card__visual {
  display: grid;
  min-width: 0;
  padding: 54px 42px;
  place-items: center;
  background:
    radial-gradient(circle at 20% 15%, rgba(147, 197, 253, 0.42), transparent 32%),
    linear-gradient(145deg, #dbeafe, #eff6ff 52%, #e0e7ff);
}

.project-gallery {
  width: min(100%, 610px);
}

.project-card__image {
  display: block;
  width: 100%;
  aspect-ratio: 16 / 10;
  border: 1px solid rgba(255, 255, 255, 0.82);
  border-radius: 18px;
  object-fit: cover;
  object-position: top;
  box-shadow: 0 24px 55px rgba(37, 99, 235, 0.2);
  transform: perspective(1100px) rotateY(2deg) rotateX(1deg);
}

.project-gallery__thumbnails {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 10px;
  margin-top: 18px;
}

.project-gallery__thumbnail {
  min-width: 0;
  padding: 7px;
  border: 1px solid rgba(148, 163, 184, 0.3);
  border-radius: 12px;
  color: #475569;
  font: inherit;
  font-size: 10px;
  font-weight: 700;
  background: rgba(255, 255, 255, 0.68);
  cursor: pointer;
  transition: 0.2s ease;
}

.project-gallery__thumbnail:hover,
.project-gallery__thumbnail.is-active {
  border-color: #2563eb;
  color: #1d4ed8;
  background: #fff;
  box-shadow: 0 8px 18px rgba(37, 99, 235, 0.14);
  transform: translateY(-2px);
}

.project-gallery__thumbnail img {
  display: block;
  width: 100%;
  aspect-ratio: 16 / 9;
  margin-bottom: 6px;
  border-radius: 7px;
  object-fit: cover;
  object-position: top;
}

.project-gallery__thumbnail span {
  display: block;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.project-card__content {
  display: flex;
  padding: 48px 44px;
  flex-direction: column;
  justify-content: center;
}

.project-card__meta {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 22px;
  color: #2563eb;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.project-card__meta small { color: #94a3b8; font-size: 12px; }
.project-card h3 { margin: 0; color: #0f172a; font-size: 38px; letter-spacing: -0.035em; }
.project-card__lead { margin: 16px 0 0; color: #334155; font-size: 17px; font-weight: 600; line-height: 1.7; }
.project-card__description { margin: 18px 0 0; color: #64748b; font-size: 14px; line-height: 1.9; }

.project-card__tech {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  margin: 26px 0 0;
  padding: 0;
  list-style: none;
}

.project-card__tech li {
  padding: 7px 11px;
  border: 1px solid #dbeafe;
  border-radius: 999px;
  color: #1d4ed8;
  font-size: 11px;
  font-weight: 700;
  background: #eff6ff;
}

.project-card__actions { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 32px; }
.project-link { display: inline-flex; gap: 8px; align-items: center; justify-content: center; padding: 12px 18px; border-radius: 999px; font-size: 13px; font-weight: 700; text-decoration: none; transition: 0.2s ease; }
.project-link:hover { transform: translateY(-2px); }
.project-link--primary { color: #fff; background: #2563eb; box-shadow: 0 10px 24px rgba(37, 99, 235, 0.22); }
.project-link--secondary { border: 1px solid #cbd5e1; color: #0f172a; background: #fff; }

@media (max-width: 900px) {
  .project-card { grid-template-columns: 1fr; }
  .project-card__visual { min-height: 470px; }
}

@media (max-width: 640px) {
  .projects { padding: 96px 20px; }
  .projects__heading { margin-bottom: 40px; }
  .projects__heading h2 { font-size: 36px; }
  .projects__heading > p:last-child { font-size: 15px; }
  .project-card { border-radius: 24px; }
  .project-card__visual { min-height: auto; padding: 34px 18px; }
  .project-card__image { transform: none; }
  .project-gallery__thumbnails { gap: 6px; }
  .project-gallery__thumbnail { padding: 5px; font-size: 9px; }
  .project-card__content { padding: 34px 24px 38px; }
  .project-card h3 { font-size: 32px; }
  .project-card__actions { flex-direction: column; }
  .project-link { width: 100%; }
}
</style>
