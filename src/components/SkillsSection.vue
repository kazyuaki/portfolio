<script setup lang="ts">
import {
  Blocks,
  Braces,
  Database,
  ServerCog,
  Sparkles,
} from "lucide-vue-next";

const skillGroups = [
  {
    title: "Frontend",
    description: "画面設計からAPI連携まで、使いやすいUIを実装します。",
    skills: ["Vue", "Nuxt", "TypeScript", "HTML", "CSS", "Axios"],
    icon: Braces,
  },
  {
    title: "Backend",
    description: "認証やCRUD、バリデーションを含むAPIを設計・実装します。",
    skills: [
      "Laravel",
      "PHP",
      "PostgreSQL",
      "MySQL（個人開発）",
      "Sanctum",
    ],
    icon: Database,
  },
  {
    title: "Development & Infrastructure",
    description: "ローカル環境の構築から、本番公開・運用まで取り組みます。",
    skills: [
      "Docker",
      "Apache",
      "Nginx（個人開発）",
      "Git",
      "GitHub（個人開発）",
      "Bitbucket",
      "VPS（個人開発）",
    ],
    icon: ServerCog,
  },
];
</script>

<template>
  <section id="skills" class="skills" aria-labelledby="skills-title">
    <div class="skills__inner">
      <header class="skills__heading">
        <p class="skills__eyebrow">Skills</p>
        <h2 id="skills-title">技術を組み合わせて、<br />アイデアを形にする。</h2>
        <p>
          実務と個人開発を通じて、フロントエンドからバックエンド、
          インフラまで幅広く経験しています。
        </p>
      </header>

      <div class="skills__grid">
        <article
          v-for="group in skillGroups"
          :key="group.title"
          class="skills__card"
        >
          <span class="skills__card-icon" aria-hidden="true">
            <component :is="group.icon" :size="23" :stroke-width="1.8" />
          </span>
          <h3>{{ group.title }}</h3>
          <p>{{ group.description }}</p>
          <ul :aria-label="`${group.title}の技術`">
            <li v-for="skill in group.skills" :key="skill">{{ skill }}</li>
          </ul>
        </article>
      </div>

      <aside class="skills__learning" aria-labelledby="learning-title">
        <div class="skills__learning-icon" aria-hidden="true">
          <Sparkles :size="23" :stroke-width="1.8" />
        </div>
        <div class="skills__learning-content">
          <p class="skills__learning-label">Currently Learning</p>
          <h3 id="learning-title">Reactを独学で学習中</h3>
          <p>
            Vueで培ったコンポーネント設計の知識と比較しながら、
            Reactの状態管理やコンポーネント設計への理解を深めています。
          </p>
        </div>
        <span class="skills__learning-badge">
          <Blocks :size="16" aria-hidden="true" />
          React
        </span>
      </aside>
    </div>
  </section>
</template>

<style scoped>
.skills {
  position: relative;
  padding: 128px 24px;
  overflow: hidden;
  scroll-margin-top: 104px;
  background:
    radial-gradient(circle at 8% 88%, rgba(96, 165, 250, 0.15), transparent 28%),
    #f8fafc;
}

.skills::before {
  position: absolute;
  top: 0;
  right: 24px;
  left: 24px;
  height: 1px;
  content: "";
  background: linear-gradient(90deg, transparent, #dbeafe, transparent);
}

.skills__inner {
  width: min(1120px, 100%);
  margin: 0 auto;
}

.skills__heading {
  max-width: 710px;
  margin-bottom: 56px;
}

.skills__eyebrow {
  margin: 0 0 18px;
  color: #2563eb;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.skills__heading h2 {
  margin: 0;
  color: #0f172a;
  font-size: clamp(36px, 4.5vw, 56px);
  font-weight: 600;
  letter-spacing: -0.035em;
  line-height: 1.35;
}

.skills__heading > p:last-child {
  margin: 24px 0 0;
  color: #64748b;
  font-size: 17px;
  line-height: 1.9;
}

.skills__grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 18px;
}

.skills__card {
  display: flex;
  min-width: 0;
  padding: 26px;
  border: 1px solid rgba(148, 163, 184, 0.2);
  border-radius: 22px;
  flex-direction: column;
  background: rgba(255, 255, 255, 0.84);
  box-shadow: 0 14px 36px rgba(15, 23, 42, 0.055);
  transition:
    border-color 0.2s ease,
    box-shadow 0.2s ease,
    transform 0.2s ease;
}

.skills__card:hover {
  border-color: rgba(96, 165, 250, 0.42);
  box-shadow: 0 20px 46px rgba(37, 99, 235, 0.1);
  transform: translateY(-4px);
}

.skills__card-icon {
  display: grid;
  width: 48px;
  height: 48px;
  margin-bottom: 24px;
  place-items: center;
  border-radius: 15px;
  color: #2563eb;
  background: #eff6ff;
}

.skills__card h3 {
  margin: 0;
  color: #0f172a;
  font-size: 19px;
}

.skills__card > p {
  min-height: 72px;
  margin: 12px 0 24px;
  color: #64748b;
  font-size: 14px;
  line-height: 1.75;
}

.skills__card ul {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  margin: auto 0 0;
  padding: 0;
  list-style: none;
}

.skills__card li {
  padding: 7px 11px;
  border: 1px solid #e2e8f0;
  border-radius: 999px;
  color: #475569;
  font-size: 12px;
  font-weight: 700;
  background: #fff;
}

.skills__learning {
  display: grid;
  grid-template-columns: auto minmax(0, 1fr) auto;
  gap: 20px;
  align-items: center;
  margin-top: 18px;
  padding: 24px 26px;
  border: 1px solid rgba(167, 139, 250, 0.24);
  border-radius: 22px;
  background:
    linear-gradient(120deg, rgba(255, 255, 255, 0.9), rgba(245, 243, 255, 0.82));
  box-shadow: 0 14px 36px rgba(76, 29, 149, 0.06);
}

.skills__learning-icon {
  display: grid;
  width: 48px;
  height: 48px;
  place-items: center;
  border-radius: 15px;
  color: #7c3aed;
  background: #ede9fe;
}

.skills__learning-label {
  margin: 0 0 5px;
  color: #7c3aed;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.skills__learning h3 {
  margin: 0;
  color: #0f172a;
  font-size: 18px;
}

.skills__learning-content > p:last-child {
  margin: 8px 0 0;
  color: #64748b;
  font-size: 14px;
  line-height: 1.7;
}

.skills__learning-badge {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 9px 14px;
  border: 1px solid rgba(124, 58, 237, 0.18);
  border-radius: 999px;
  color: #6d28d9;
  font-size: 13px;
  font-weight: 700;
  background: rgba(255, 255, 255, 0.72);
}

@media (max-width: 900px) {
  .skills__grid {
    grid-template-columns: 1fr;
  }

  .skills__card > p {
    min-height: auto;
  }
}

@media (max-width: 640px) {
  .skills {
    padding: 80px 20px;
  }

  .skills::before {
    right: 20px;
    left: 20px;
  }

  .skills__heading {
    margin-bottom: 40px;
  }

  .skills__heading h2 {
    font-size: 34px;
  }

  .skills__heading h2 br {
    display: none;
  }

  .skills__heading > p:last-child {
    font-size: 16px;
  }

  .skills__card {
    padding: 22px;
  }

  .skills__learning {
    grid-template-columns: auto minmax(0, 1fr);
    padding: 20px;
  }

  .skills__learning-badge {
    grid-column: 1 / -1;
    justify-self: start;
  }
}

@media (prefers-reduced-motion: reduce) {
  .skills__card {
    transition: none;
  }
}
</style>
