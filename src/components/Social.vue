<template>
  <div class="social-block">
    <h2 class="social-block__title">Search through more than 11 million<br /> social media profiles</h2>
    <p class="social-block__subtitle">Heepsy’s search filters help you find exactly what you’re looking for, and<br /> our influencer reports provide you with the metrics</p>

    <div class="social-block__numbers">
      <div v-for="item in numbers" :key="item.id" class="social-block__numbers_item">
        <span class="number">{{ item.number }}</span>
        <p class="text">{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

const numbers = reactive([
  { id: 1, number: '2260', text: 'Satisfied Brands' },
  { id: 2, number: '1324', text: 'Satisfied Clients' },
  { id: 3, number: '3453', text: 'Sponsored' },
  { id: 4, number: '9768', text: 'Completed' },
])
</script>

<style lang="scss" scoped>
.social-block {
  text-align: center;
  &__title {
    font-size: 40px;
    font-weight: 600;
    line-height: 50px;
    color: $white;
  }

  &__subtitle {
    font-size: 16px;
    color: $light-gray;
    line-height: 28px;
    margin-top: 20px;
  }
  &__numbers {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    gap: 100px;
    &_item {
      
      .number {
        color: $white;
        font-size: 40px;
        font-weight: 600;
      }
      .text {
        color: $light-gray;
      }
    }
  }
}
</style>