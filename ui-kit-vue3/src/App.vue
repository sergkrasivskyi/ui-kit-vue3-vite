<script setup>
import LayoutHeader from '@/components/layout/Header.vue'
import LayoutSidebar from '@/components/layout/Sidebar.vue'
import { ref } from 'vue';
const isOpenMenu = ref(false);
const toggleMenu = () => {
  isOpenMenu.value = !isOpenMenu.value;
}
</script>

<template>
  <div class="container">
    <div class="sidebar-toggle" @click="toggleMenu">&#5125;</div>
    <layout-header />
    <layout-sidebar :openSidebar="isOpenMenu" />
    <div :class="['content', {content_full: !isOpenMenu}]">
      <router-view></router-view>

    </div>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
<style lang="scss">
@import './styles/global.scss';

.sidebar-toggle {
  position: fixed;
  left: 0;
  width: 1rem;
  background-color: var(--primary);
  height: 100%;
  top: 5rem;
  z-index: 1;
  cursor: pointer;
  color: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {}

.content {
  margin-left: 15.65rem;

  &_full {
    margin: 0;
  }
}
</style>
