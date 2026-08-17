<script setup lang="ts">
import { Menu, X } from "lucide-vue-next";
import { onBeforeUnmount, ref } from "vue";

const isMenuOpen = ref(false);

const navigationItems = [
  { label: "About", href: "#about" },
  { label: "Experience", href: "#experience" },
  { label: "Skills", href: "#skills" },
  { label: "Projects", href: "#projects" },
  { label: "Contact", href: "#contact" },
];

const closeMenu = () => {
  isMenuOpen.value = false;
};

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const handleEscape = (event: KeyboardEvent) => {
  if (event.key === "Escape") {
    closeMenu();
  }
};

window.addEventListener("keydown", handleEscape);

onBeforeUnmount(() => {
  window.removeEventListener("keydown", handleEscape);
});
</script>

<template>
  <header class="site-header">
    <div class="site-header__inner">
      <a class="site-header__logo" href="#top" @click="closeMenu">
        <span class="site-header__logo-mark" aria-hidden="true">KY</span>
        <span>Kazuaki Yamamoto</span>
      </a>

      <button
        class="site-header__menu-button"
        type="button"
        :aria-expanded="isMenuOpen"
        aria-controls="primary-navigation"
        :aria-label="isMenuOpen ? 'メニューを閉じる' : 'メニューを開く'"
        @click="toggleMenu"
      >
        <X v-if="isMenuOpen" :size="22" aria-hidden="true" />
        <Menu v-else :size="22" aria-hidden="true" />
      </button>

      <nav
        id="primary-navigation"
        :class="['site-header__nav', { 'site-header__nav--open': isMenuOpen }]"
        aria-label="メインナビゲーション"
      >
        <a
          v-for="item in navigationItems"
          :key="item.href"
          :href="item.href"
          @click="closeMenu"
        >
          {{ item.label }}
        </a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.site-header {
  position: fixed;
  top: 16px;
  right: 0;
  left: 0;
  z-index: 100;
  padding: 0 24px;
}

.site-header__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: min(1120px, 100%);
  min-height: 64px;
  margin: 0 auto;
  padding: 0 18px;
  border: 1px solid rgba(148, 163, 184, 0.22);
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.68);
  box-shadow: 0 12px 36px rgba(15, 23, 42, 0.08);
  backdrop-filter: blur(18px) saturate(150%);
  -webkit-backdrop-filter: blur(18px) saturate(150%);
}

.site-header__logo {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  color: #0f172a;
  font-size: 15px;
  font-weight: 700;
  letter-spacing: -0.01em;
  text-decoration: none;
}

.site-header__logo-mark {
  display: grid;
  width: 34px;
  height: 34px;
  place-items: center;
  border-radius: 11px;
  color: #fff;
  font-size: 12px;
  letter-spacing: 0.04em;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  box-shadow: 0 8px 18px rgba(37, 99, 235, 0.24);
}

.site-header__nav {
  display: flex;
  align-items: center;
  gap: 6px;
}

.site-header__nav a {
  padding: 9px 13px;
  border-radius: 999px;
  color: #475569;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
  transition:
    color 0.2s ease,
    background 0.2s ease,
    transform 0.2s ease;
}

.site-header__nav a:hover,
.site-header__nav a:focus-visible {
  color: #1d4ed8;
  background: rgba(219, 234, 254, 0.7);
  transform: translateY(-1px);
  outline: none;
}

.site-header__menu-button {
  display: none;
  align-items: center;
  justify-content: center;
  width: 42px;
  height: 42px;
  padding: 0;
  border: 1px solid rgba(148, 163, 184, 0.25);
  border-radius: 13px;
  color: #334155;
  background: rgba(255, 255, 255, 0.76);
  cursor: pointer;
}

@media (max-width: 720px) {
  .site-header {
    top: 10px;
    padding: 0 12px;
  }

  .site-header__inner {
    position: relative;
    min-height: 58px;
    padding: 0 12px 0 14px;
    border-radius: 17px;
  }

  .site-header__menu-button {
    display: inline-flex;
  }

  .site-header__nav {
    position: absolute;
    top: calc(100% + 10px);
    right: 0;
    left: 0;
    display: grid;
    gap: 4px;
    padding: 10px;
    border: 1px solid rgba(148, 163, 184, 0.22);
    border-radius: 17px;
    visibility: hidden;
    opacity: 0;
    background: rgba(255, 255, 255, 0.92);
    box-shadow: 0 18px 42px rgba(15, 23, 42, 0.12);
    backdrop-filter: blur(18px);
    transform: translateY(-8px);
    transition:
      visibility 0.2s ease,
      opacity 0.2s ease,
      transform 0.2s ease;
  }

  .site-header__nav--open {
    visibility: visible;
    opacity: 1;
    transform: translateY(0);
  }

  .site-header__nav a {
    padding: 12px 14px;
    text-align: center;
  }
}

@media (max-width: 380px) {
  .site-header__logo > span:last-child {
    font-size: 13px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .site-header__nav,
  .site-header__nav a {
    transition: none;
  }
}
</style>
