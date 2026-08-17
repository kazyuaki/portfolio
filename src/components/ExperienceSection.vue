<script setup lang="ts">
import {
  CheckCircle2,
  GraduationCap,
  Music2,
  ShieldCheck,
} from "lucide-vue-next";

const applications = [
  {
    title: "学習塾向け管理Webアプリ",
    description:
      "管理者・講師・生徒／保護者が利用する、教育現場の業務を支えるWebアプリケーションです。",
    icon: GraduationCap,
  },
  {
    title: "音楽教室向け管理Webアプリ",
    description:
      "管理者・講師・生徒／保護者が利用する、音楽教育に関する業務管理Webアプリケーションです。",
    icon: Music2,
  },
];

const responsibilities = [
  "既存サービスへの新規機能追加",
  "既存機能の修正・改善対応",
  "E2Eシナリオテストの実施",
  "UAT（ユーザー受け入れテスト）対応",
];

const technologies = [
  "Laravel",
  "Vue",
  "PostgreSQL",
  "Apache",
  "Bitbucket",
];
</script>

<template>
  <section id="experience" class="experience" aria-labelledby="experience-title">
    <div class="experience__inner">
      <header class="experience__heading">
        <p class="experience__eyebrow">Experience</p>
        <h2 id="experience-title">既存サービスを理解し、<br />着実に改善する。</h2>
        <p>
          実務では、すでに利用されている教育系Webアプリケーションの
          機能追加・改修・テストに携わっています。
        </p>
      </header>

      <article class="experience__role">
        <div class="experience__timeline" aria-hidden="true">
          <span></span>
        </div>

        <div class="experience__role-content">
          <div class="experience__role-header">
            <div>
              <p class="experience__period">2025.12 — Present</p>
              <h3>Webアプリケーション開発・保守</h3>
            </div>
            <span class="experience__status">参画中</span>
          </div>

          <div class="experience__applications">
            <section
              v-for="application in applications"
              :key="application.title"
              class="experience__application"
            >
              <span class="experience__application-icon" aria-hidden="true">
                <component :is="application.icon" :size="22" :stroke-width="1.8" />
              </span>
              <div>
                <h4>{{ application.title }}</h4>
                <p>{{ application.description }}</p>
              </div>
            </section>
          </div>

          <div class="experience__details">
            <div>
              <p class="experience__label">Responsibilities</p>
              <ul class="experience__responsibilities">
                <li v-for="responsibility in responsibilities" :key="responsibility">
                  <CheckCircle2 :size="17" aria-hidden="true" />
                  <span>{{ responsibility }}</span>
                </li>
              </ul>
            </div>

            <div>
              <p class="experience__label">Technology</p>
              <ul class="experience__technologies" aria-label="実務で使用している技術">
                <li v-for="technology in technologies" :key="technology">
                  {{ technology }}
                </li>
              </ul>
            </div>
          </div>

          <aside class="experience__confidentiality">
            <ShieldCheck :size="19" :stroke-width="1.8" aria-hidden="true" />
            <p>
              守秘義務に配慮し、企業名・サービス名・画面・内部仕様は掲載せず、
              公開可能な範囲で業務内容を記載しています。
            </p>
          </aside>
        </div>
      </article>
    </div>
  </section>
</template>

<style scoped>
.experience {
  position: relative;
  padding: 128px 24px;
  overflow: hidden;
  scroll-margin-top: 104px;
  background:
    radial-gradient(circle at 88% 18%, rgba(96, 165, 250, 0.14), transparent 27%),
    #f8fafc;
}

.experience::before {
  position: absolute;
  top: 0;
  right: 24px;
  left: 24px;
  height: 1px;
  content: "";
  background: linear-gradient(90deg, transparent, #dbeafe, transparent);
}

.experience__inner {
  width: min(1120px, 100%);
  margin: 0 auto;
}

.experience__heading {
  max-width: 740px;
  margin-bottom: 56px;
}

.experience__eyebrow,
.experience__label {
  margin: 0 0 18px;
  color: #2563eb;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.experience__heading h2 {
  margin: 0;
  color: #0f172a;
  font-size: clamp(36px, 4.5vw, 56px);
  font-weight: 600;
  letter-spacing: -0.035em;
  line-height: 1.35;
}

.experience__heading > p:last-child {
  margin: 24px 0 0;
  color: #64748b;
  font-size: 17px;
  line-height: 1.9;
}

.experience__role {
  display: grid;
  grid-template-columns: 34px minmax(0, 1fr);
}

.experience__timeline {
  position: relative;
}

.experience__timeline::after {
  position: absolute;
  top: 23px;
  bottom: 0;
  left: 8px;
  width: 2px;
  content: "";
  background: linear-gradient(#60a5fa, rgba(96, 165, 250, 0.08));
}

.experience__timeline span {
  position: relative;
  z-index: 1;
  display: block;
  width: 18px;
  height: 18px;
  margin-top: 10px;
  border: 5px solid #dbeafe;
  border-radius: 50%;
  background: #2563eb;
  box-shadow: 0 0 0 5px #f8fafc;
}

.experience__role-content {
  padding: 34px;
  border: 1px solid rgba(148, 163, 184, 0.22);
  border-radius: 26px;
  background: rgba(255, 255, 255, 0.88);
  box-shadow: 0 20px 54px rgba(15, 23, 42, 0.07);
}

.experience__role-header {
  display: flex;
  gap: 24px;
  align-items: flex-start;
  justify-content: space-between;
}

.experience__period {
  margin: 0 0 8px;
  color: #2563eb;
  font-size: 13px;
  font-weight: 800;
  letter-spacing: 0.06em;
}

.experience__role-header h3 {
  margin: 0;
  color: #0f172a;
  font-size: clamp(24px, 3vw, 32px);
  letter-spacing: -0.025em;
}

.experience__status {
  flex: 0 0 auto;
  padding: 8px 13px;
  border: 1px solid #bbf7d0;
  border-radius: 999px;
  color: #15803d;
  font-size: 12px;
  font-weight: 700;
  background: #f0fdf4;
}

.experience__applications {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 14px;
  margin-top: 32px;
}

.experience__application {
  display: grid;
  grid-template-columns: auto minmax(0, 1fr);
  gap: 16px;
  padding: 22px;
  border: 1px solid #e2e8f0;
  border-radius: 19px;
  background: #f8fafc;
}

.experience__application-icon {
  display: grid;
  width: 44px;
  height: 44px;
  place-items: center;
  border-radius: 14px;
  color: #2563eb;
  background: #dbeafe;
}

.experience__application h4 {
  margin: 1px 0 8px;
  color: #1e293b;
  font-size: 16px;
}

.experience__application p {
  margin: 0;
  color: #64748b;
  font-size: 13px;
  line-height: 1.75;
}

.experience__details {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 40px;
  margin-top: 34px;
  padding-top: 32px;
  border-top: 1px solid #e2e8f0;
}

.experience__label {
  margin-bottom: 16px;
  color: #64748b;
  font-size: 11px;
}

.experience__responsibilities,
.experience__technologies {
  margin: 0;
  padding: 0;
  list-style: none;
}

.experience__responsibilities {
  display: grid;
  gap: 12px;
}

.experience__responsibilities li {
  display: flex;
  gap: 9px;
  align-items: center;
  color: #475569;
  font-size: 14px;
}

.experience__responsibilities svg {
  flex: 0 0 auto;
  color: #2563eb;
}

.experience__technologies {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.experience__technologies li {
  padding: 8px 12px;
  border: 1px solid #dbeafe;
  border-radius: 999px;
  color: #1d4ed8;
  font-size: 12px;
  font-weight: 700;
  background: #eff6ff;
}

.experience__confidentiality {
  display: flex;
  gap: 10px;
  align-items: flex-start;
  margin-top: 32px;
  padding: 16px 18px;
  border: 1px solid #e2e8f0;
  border-radius: 15px;
  color: #64748b;
  background: #f8fafc;
}

.experience__confidentiality svg {
  flex: 0 0 auto;
  margin-top: 2px;
  color: #475569;
}

.experience__confidentiality p {
  margin: 0;
  font-size: 12px;
  line-height: 1.7;
}

@media (max-width: 760px) {
  .experience {
    padding: 96px 20px;
  }

  .experience__heading {
    margin-bottom: 40px;
  }

  .experience__heading h2 {
    font-size: 36px;
  }

  .experience__heading > p:last-child {
    font-size: 15px;
  }

  .experience__role {
    grid-template-columns: 1fr;
  }

  .experience__timeline {
    display: none;
  }

  .experience__role-content {
    padding: 26px 20px;
    border-radius: 22px;
  }

  .experience__applications,
  .experience__details {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 480px) {
  .experience__role-header {
    flex-direction: column;
  }

  .experience__application {
    padding: 18px;
  }
}
</style>
