<template>
  <div class="footer">
    <div class="footer__nav">
      <Nav :links="linksHome" :title="'Home'" />
      <Nav :links="linksResources" :title="'Resources'" />
      <Nav :links="linksCommunity" :title="'Community'" />
      <Nav :links="linksMembers" :title="'Main links'" />
    </div>

    <div class="footer__subscribe">
      <h2 class="title">Subscribe Cirkle Newsletter</h2>
      <p class="subtitle">Subscribe to be the first one to know about updates. Enter your email</p>

      <div class="field">
        <input type="email" placeholder="Enter your email" class="field__input">
        <button type="button" class="btn-subscribe">Subscribe</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import Nav from './Nav.vue'
import { reactive } from 'vue'

const linksHome = reactive([
  { id: 1, name: 'Home', link: '/' },
  { id: 2, name: 'Community', link: '/' },
  { id: 3, name: 'Events', link: '/' },
  { id: 4, name: 'Contact', link: '/' },
])

const linksResources = reactive([
  { id: 1, name: 'Blog', link: '/' },
  { id: 2, name: 'News', link: '/' },
  { id: 3, name: 'Guides', link: '/' },
  { id: 4, name: 'Help Center', link: '/' },
])

const linksCommunity = reactive([
  { id: 1, name: 'NewsFeed', link: '/' },
  { id: 2, name: 'Profile', link: '/' },
  { id: 3, name: 'Friends', link: '/' },
  { id: 4, name: 'Forums', link: '/' },
])

const linksMembers = reactive([
  { id: 1, name: 'Members', link: '/' },
  { id: 2, name: 'Activity', link: '/' },
  { id: 3, name: 'Groups', link: '/' },
  { id: 4, name: 'Private Group', link: '/' },
])
</script>

<style lang="scss" scoped>
.footer {
  display: flex;
  justify-content: space-between;

  &__nav {
    display: flex;
    justify-content: space-between;
    gap: 80px;
  }

  &__subscribe {
    width: 340px;
    color: $white;

    .title {
      font-weight: 500;
      font-size: 20px;
    }

    .subtitle {
      font-size: 16px;
      margin: 30px 0;
      line-height: 28px;
    }

    .field {
      display: flex;
      gap: 10px;
      position: relative;

      &__input {
        width: 100%;
        background-color: transparent;
        border: 2px solid $white;
        border-radius: 12px;
        padding: 15px;

        &::placeholder {
          font-size: 14px;
          color: rgba(113, 113, 121, 1);
        }
      }

      .btn-subscribe {
        position: absolute;
        top: 0;
        right: 0;
        background-color: $white;
        border: 0;
        color: $black;
        border-radius: 12px;
        padding: 15px 20px;
        cursor: pointer;
        font-size: 16px;
        font-weight: 500;
      }
    }
  }
}

@media screen and (max-width: 1070px) {
  .footer {
    &__nav {
      gap: 40px;
    }
  }
}
</style>