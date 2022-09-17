<template>
  <div :class="['sidebar', {sidebar_isopen: openSidebar}]">
    <router-link
    class="sidebar__link"
    v-for="link in links"
    :key="link.name"
    :to="link.href">{{link.name}}
    </router-link>
  </div>
</template>

<script setup>
import { ref } from "vue"
const props = defineProps({
  openSidebar: {
    type: Boolean,
    required: true
  },
})
const links = ref([
  { name: "Typography", href: "/typography" },
  { name: "Button", href: "/button" }
])
</script>

<style lang="scss" scoped>
.sidebar {
  width: 15.65rem;
  background-color: mediumaquamarine;
  left: 0;
  top: 4rem;
  position: fixed;
  transition: 0.2s ease;
  transform: translateX(-15.65rem);

  &_isopen {
    transform: translateX(1rem);
  }

  &__link {
    display: block;
    border-radius: 1.5rem;

    &:hover {
      color: var(--primary);
    }
  }
}
</style>
