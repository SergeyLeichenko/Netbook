<template>
  <div class="hero-block">
    <div class="hero-block__text">
      <button type="button" class="btn-community">Netbook community</button>

      <h1 class="title">Your Solutions For Community!</h1>
      <p class="subtitle">
        More than 2 billion people in over countries use socibook to stay in touch with friends & family.
      </p>

      <div class="buttons">
        <button type="button" class="btn about-more">About More</button>
        <button type="button" class="btn">Invite Friend</button>
      </div>
    </div>
    <div class="hero-block__image">
      <img src="../assets/images/Iamge.png" alt="hero">
    </div>
  </div>
</template>
<script>
export default {

}
</script>
<style lang="scss" scoped>
.hero-block {
  display: flex;
  justify-content: space-between;

  &__text {
    width: 515px;

    .btn-community {
      width: 177px;
      background-color: rgb(0 83 195 / 10%);
      color: $blue;
      font-size: 12px;
      font-weight: 500;
      padding: 10px 0;
      border: 0;
      border-radius: 8px;
      outline: none;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
    }

    .title {
      font-weight: 700;
      font-size: 56px;
      margin: 30px 0;
    }

    .subtitle {
      font-size: 18px;
      line-height: 28px;
      color: $light-gray;
      margin-bottom: 30px;
    }

    .buttons {
      display: flex;

      .btn {
        width: 162px;
      }

      .about-more {
        margin-right: 20px;
      }
    }
  }
  &__image {
    width: 585px;
    height: auto;
    img {
      width: 100%;
      height: 100%;
    }
  }
}
</style>