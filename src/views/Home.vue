<template>
  <div>
    <Header />

    <section class="hero padding">
      <div class="container">
        <Hero />
      </div>
    </section>

    <section class="form-order padding">
      <div class="container">
        <h2 class="form-order__title">Замовити послугу</h2>
        <Form />
      </div>
    </section>

    <section class="social padding">
      <div class="container">
        <Social />
      </div>
    </section>

    <section class="connecting padding">
      <div class="container">
        <Connecting />
      </div>
    </section>

    <section class="footer-top padding">
      <div class="container">
        <FooterTop />
      </div>
    </section>

    <section class="footer-down">
      <div class="container">
        <div class="footer-block">
          <p class="footer-block__text">Besnik Creative Agency.</p>
          <div class="footer-block__logo">
            <img src="../assets/images/logo-white.svg" alt="logo">
          </div>
          
          <Socials />

        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import Header from "@/components/Header.vue";
import Hero from "@/components/Hero.vue"
import Form from "@/components/Form.vue"
import Social from "@/components/Social.vue"
import Connecting from "@/components/Connecting.vue"
import FooterTop from "@/components/footer/FooterTop.vue"
import Socials from "@/components/footer/Socials.vue"
</script>

<style lang="scss" scoped>
.hero {
  background: linear-gradient(rgba(255, 255, 255, 1), rgba(212, 231, 254, 1));
}

.form-order {
  &__title {
    text-align: center;
    font-size: 36px;
    font-weight: 600;
    margin-bottom: 100px;
  }
}

.social {
  background-color: $violet;
}

.footer-top {
  background-color: $bg-footer-top;
}

.footer-down {
  background-color: $bg-footer-down;
  padding: 30px 0;
  .footer-block {
    display: flex;
    justify-content: space-between;
    align-items: center;
    &__text {
      font-size: 14px;
      color: $white;
    }
  }
}
</style>