<template>
  <div>
    <div class="header container">
      <div class="header__logo-nav">
        <div class="logo">
          <img src="../assets/images/logo.svg" alt="logo" title="logo">
        </div>
        <div class="nav">

          <Navigation />

        </div>
      </div>

      <div class="header__search-btn">
        <div class="search">
          <img src="../assets/images/search.svg" alt="search" class="icon-search">
          <input type="text" placeholder="Search Hare">
        </div>
        <div class="btn-logIn">
          <button type="button" class="btn">Log in</button>
        </div>
      </div>
    </div>
    <div class="border"></div>
  </div>
</template>

<script setup>
import Navigation from '@/components/Navigation.vue';
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 0;

  &__logo-nav {
    display: flex;
    align-items: center;

    .nav {
      margin-left: 40px;
    }
  }

  &__search-btn {
    display: flex;

    .search {
      display: flex;
      align-items: center;
      max-width: 105px;
      margin-right: 40px;
      border-bottom: 1px solid $light-gray;
      .icon-search {
        margin-right: 10px;
      }

      input {
        width: 100%;
        border: none;
        outline: none;
        &::placeholder {
          font-size: 12px;
        }
      }
    }
    .btn-logIn {
      .btn {
        width: 123px;
      }
    }
  }
}

.border {
  border-bottom: 1px solid $blue;
}

@media screen and (min-width: 1000px) {
  .header {
    padding: 20px;
  }
}
</style>