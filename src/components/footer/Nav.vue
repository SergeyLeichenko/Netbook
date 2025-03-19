<template>
  <nav class="nav">
    <p class="nav__title">{{ title }}</p>
    <ul class="nav__list">
      <li v-for="item in links" :key="item.id" class="nav__list_item">
        <router-link :to="item.link" class="nav__list_item_link">{{ item.name }}</router-link>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { defineProps } from 'vue'

defineProps({
  links: {
    type: Array,
    required: true
  },
  title: {
    type: String,
    required: true
  }
})
</script>

<style lang="scss" scoped>
.nav {
  color: $white;

  &__title {
    font-size: 20px;
    font-weight: 500;
    margin-bottom: 30px;
  }

  &__list {
    list-style: none;
    padding: 0;
    margin: 0;

    &_item {
      margin-bottom: 20px;

      &_link {
        text-decoration: none;
        font-size: 16px;
        color: $white;
      }
    }
  }
}
</style>