<template>
  <nav>
    <ul class="navbar">
      <li v-for="item in links" :key="item.id" class="navbar__item">
        <router-link :to="item.link" class="navbar__item_link">{{ item.name }}</router-link>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import {reactive } from 'vue'

const links = reactive([
  { id: 1, name: 'Home', link: '/' },
  { id: 2, name: 'Community', link: '' },
  { id: 3, name: 'Blog', link: '' },
  { id: 4, name: 'Events', link: '' },
])
</script>

<style lang="scss" scoped>
@use '@/assets/style/variables.scss' as *;

.navbar {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;

  &__item {
    margin-left: 20px;

    &_link {
      text-decoration: none;
      color: $light-gray;
      &:hover {
        font-weight: 600;
        color: $black;
      }
    }
  }
}
</style>