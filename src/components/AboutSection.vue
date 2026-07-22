<script setup lang="ts">
import { Layers3, MonitorSmartphone, Rocket } from "lucide-vue-next";

const values = [
  {
    title: "使いやすさ",
    description:
      "迷わず操作でき、必要な情報へ素早くたどり着けるUIを意識しています。",
    icon: MonitorSmartphone,
  },
  {
    title: "保守しやすい設計",
    description:
      "責務を分けたコンポーネント設計と、読みやすく変更しやすいコードを大切にしています。",
    icon: Layers3,
  },
  {
    title: "公開までやり切る",
    description:
      "設計・実装だけでなく、Docker環境の構築やVPSへのデプロイまで取り組みます。",
    icon: Rocket,
  },
];
</script>

<template>
  <section id="about" class="about" aria-labelledby="about-title">
    <div class="about__inner">
      <div class="about__heading">
        <p class="about__eyebrow">About me</p>
        <h2 id="about-title">つくる理由を、<br />使いやすさにつなげる。</h2>
      </div>

      <div class="about__content">
        <div class="about__introduction">
          <p>
            2025年12月からWebアプリケーション開発の実務に携わり、
            Laravel・Vueを使用した開発経験を積んでいます。
          </p>
          <p>
            日々の学習や業務で増えていくタスクを整理したいという思いから、
            タスク管理アプリ「Task Flow」を開発しました。
          </p>
          <p>
            個人開発ではNuxtやDockerも活用し、フロントエンドからバックエンド、
            インフラまで一貫して取り組んでいます。機能を実装するだけでなく、
            使う人が迷わず操作でき、あとから改善しやすい設計を心掛けています。
          </p>
        </div>

        <ul class="about__values" aria-label="開発で大切にしていること">
          <li v-for="value in values" :key="value.title" class="about__value-card">
            <span class="about__value-icon" aria-hidden="true">
              <component :is="value.icon" :size="21" :stroke-width="1.8" />
            </span>
            <div>
              <h3>{{ value.title }}</h3>
              <p>{{ value.description }}</p>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  position: relative;
  padding: 128px 24px;
  overflow: hidden;
  scroll-margin-top: 104px;
  background:
    radial-gradient(circle at 92% 12%, rgba(147, 197, 253, 0.18), transparent 26%),
    #fff;
}

.about::before {
  position: absolute;
  top: 0;
  right: 24px;
  left: 24px;
  height: 1px;
  content: "";
  background: linear-gradient(90deg, transparent, #dbeafe, transparent);
}

.about__inner {
  display: grid;
  grid-template-columns: minmax(260px, 0.78fr) minmax(0, 1.22fr);
  gap: clamp(56px, 8vw, 112px);
  width: min(1120px, 100%);
  margin: 0 auto;
}

.about__heading {
  align-self: start;
  position: sticky;
  top: 120px;
}

.about__eyebrow {
  margin: 0 0 18px;
  color: #2563eb;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.about__heading h2 {
  margin: 0;
  color: #0f172a;
  font-size: clamp(36px, 4.5vw, 56px);
  font-weight: 600;
  letter-spacing: -0.035em;
  line-height: 1.35;
}

.about__content {
  min-width: 0;
}

.about__introduction {
  display: grid;
  gap: 20px;
}

.about__introduction p {
  margin: 0;
  color: #475569;
  font-size: 17px;
  line-height: 2;
}

.about__values {
  display: grid;
  gap: 14px;
  margin: 48px 0 0;
  padding: 0;
  list-style: none;
}

.about__value-card {
  display: grid;
  grid-template-columns: auto minmax(0, 1fr);
  gap: 18px;
  padding: 22px;
  border: 1px solid rgba(148, 163, 184, 0.2);
  border-radius: 20px;
  background: rgba(248, 250, 252, 0.78);
  box-shadow: 0 12px 32px rgba(15, 23, 42, 0.045);
  transition:
    border-color 0.2s ease,
    box-shadow 0.2s ease,
    transform 0.2s ease;
}

.about__value-card:hover {
  border-color: rgba(96, 165, 250, 0.42);
  box-shadow: 0 18px 40px rgba(37, 99, 235, 0.09);
  transform: translateY(-3px);
}

.about__value-icon {
  display: grid;
  width: 44px;
  height: 44px;
  place-items: center;
  border-radius: 14px;
  color: #2563eb;
  background: #eff6ff;
}

.about__value-card h3 {
  margin: 1px 0 7px;
  color: #0f172a;
  font-size: 16px;
}

.about__value-card p {
  margin: 0;
  color: #64748b;
  font-size: 14px;
  line-height: 1.75;
}

@media (max-width: 820px) {
  .about {
    padding: 96px 24px;
  }

  .about__inner {
    grid-template-columns: 1fr;
    gap: 44px;
  }

  .about__heading {
    position: static;
  }

  .about__heading h2 br {
    display: none;
  }
}

@media (max-width: 520px) {
  .about {
    padding: 80px 20px;
  }

  .about::before {
    right: 20px;
    left: 20px;
  }

  .about__heading h2 {
    font-size: 34px;
  }

  .about__introduction p {
    font-size: 16px;
    line-height: 1.9;
  }

  .about__values {
    margin-top: 36px;
  }

  .about__value-card {
    gap: 14px;
    padding: 18px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .about__value-card {
    transition: none;
  }
}
</style>
