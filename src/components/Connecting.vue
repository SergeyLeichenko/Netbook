<template>
  <div class="connecting-block">

    <div class="connecting-block__ratting">
      <div class="ratting">
        <img src="../assets/images/star.svg" alt="star" class="icon">
        <p class="ratting_text">4.8 Rating</p>
      </div>

      <div class="users">
        <img src="../assets/images/people.svg" alt="avatar" class="avatar" />
        <p class="users_text"><span class="number-blue">+836k</span> Members</p>
      </div>

      <p class="text">
        More than 2 billion we people over countries use socibooks we to stay in touch with friends.
      </p>

      <div class="button">
        <button type="button" class="join">Join Our Community</button>
        <img src="../assets/images/ArrowRightBlue.svg" alt="arrow right" class="arrow">
      </div>
    </div>

    <div class="connecting-block__ratting">
      <div class="ratting">
        <img src="../assets/images/Trophy.svg" alt="Trophy" class="icon">
        <p class="ratting_text">Awwwards</p>
      </div>

      <div class="users">
        <img src="../assets/images/github.svg" alt="github" />
        <p class="users_text">Best of <span class="number-blue">2021</span> on Github</p>
      </div>

      <p class="text">
        More than 2 billion we people over countries use socibooks we to stay in touch with friends.
      </p>

      <div class="button">
        <button type="button" class="join awards">Go To Awards</button>
        <img src="../assets/images/ArrowRightBlack.svg" alt="arrow right" class="arrow">
      </div>
    </div>

    <div class="connecting-block__achievement">
      <p class="text-top">Our Achievement</p>
      <h2 class="title">We are Connecting You The Digital Life.</h2>
      <p class="text">The scope the Social Media becomes crucial Is helps the business to directly engage with their needs and wants.</p>
      <div class="button-discover">
        <button type="button" class="btn" @mouseover="isArrow = true" @mouseleave="isArrow = false">Discover me
          <img v-if="isArrow" src="../assets/images/ArrowRightBlue.svg" alt="arrow right" class="arrow">
          <img v-else src="../assets/images/ArrowRightWhite.svg" alt="arrow right" class="arrow">
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isArrow = ref(true);
</script>

<style lang="scss" scoped>
.connecting-block {
  display: flex;
  justify-content: space-between;
  gap: 20px;

  &__ratting {
    width: 335px;
    padding: 30px;
    font-size: 16px;
    color: $black;
    box-shadow: 0px 26px 49px rgba(146, 165, 184, 0.14);
    border-radius: 14px;
    background: linear-gradient(rgba(185, 185, 185, 0.13), rgba(94, 94, 94, 0.37));

    .ratting {
      display: flex;
      align-items: center;

      .icon {
        width: 28px;
        height: 28px;
      }

      &_text {
        font-size: 20px;
        font-weight: 500;
        margin-left: 10px;
      }
    }

    .users {
      display: flex;
      align-items: center;
      margin: 30px 0;

      &_text {
        margin-left: 10px;

        .number-blue {
          color: $blue;
          font-weight: 600;
        }
      }
    }

    .text {
      color: $text;
      line-height: 26px;
    }

    .button {
      display: flex;
      align-items: center;
      margin-top: 30px;

      .join {
        background-color: transparent;
        border: none;
        color: $blue;
        font-size: 16px;
        font-weight: 500;
        cursor: pointer;
        outline: none;
        margin-right: 15px;
      }

      .awards {
        color: $black;
      }
    }
  }

  &__achievement {
    width: 335px;

    .text-top {
      font-size: 18px;
      color: $blue;
      font-weight: 500;
    }

    .title {
      font-size: 36px;
      font-weight: 700;
      margin: 20px 0;
    }

    .text {
      color: $text;
      line-height: 26px;
    }

    .button-discover {
      margin-top: 30px;
      display: flex;
      align-items: center;

      .btn {
        width: 192px;
        .arrow {
          margin-left: 20px;
        }
      }
    }
  }
}
</style>