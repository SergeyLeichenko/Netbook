<template>
  <div class="footer-block__socials">
    <ul class="footer-block__socials_list">
      <li v-for="item in socials" :key="item.id" class="footer-block__socials_list_item">
        <router-link :to="item.link" class="footer-block__socials_list_item_link">
          <img :src="getImageUrl(item.name)" :alt="`${item.name} icon`">
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const socials = ref([
  { id: 1, name: 'Twitter', link: '/' },
  { id: 2, name: 'instagram', link: '/' },
  { id: 3, name: 'facebook', link: '/' },
  { id: 4, name: 'Linkedin', link: '/' },
])

const images = import.meta.glob('../../assets/images/*.svg', { eager: true })

const getImageUrl = (name) => {
  return images[`../../assets/images/${name}.svg`]?.default || ''
}
</script>

<style lang="scss" scoped>
.footer-block__socials {
  display: flex;
  gap: 10px;
  &_list {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
    gap: 15px;
  }
}
</style>