<template>
  <div class="nav">
    <div class="nav__menu">
      <div class="nav__logo"></div>
      <div class="nav__item">Кофе</div>
      <div class="nav__item">Аксессуары</div>
    </div>
    <div class="nav__cart cart">
      <div class="cart__logo">
        <div class="cart__bage"></div>
      </div>
      <div class="cart__text">5662P</div>
    </div>

    <div class="nav__burger-menu"></div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@media (max-width: 1200px) {
  .nav {
    &__logo {
      flex: 1 0 100%;
    }

    &__item {
      font-size: 1.8rem !important;
      line-height: 2.5rem !important;
      margin: 3.7rem 3.5rem 0 0 !important;
    }

    &__burger-menu {
      display: flex !important;
      width: 3rem;
      height: 2rem;
      margin: 0.4rem 0 0 2rem;
      background: url(../assets/img/burger_menu.svg) left center no-repeat;
    }
  }

  .cart {
    padding: 0 !important;
    height: 3rem;
    width: 5rem;

    &__text {
      display: none;
    }

    &__logo {
      background: url(../assets/img/cart_small.svg) left center no-repeat !important;
      height: 1.8rem !important;
      width: 2.1rem !important;
    }
  }
}

.nav {
  display: flex;
  display: 100%;
  justify-content: space-between;
  &__menu {
    display: flex;
    flex-wrap: wrap;
  }

  &__item {
    font-family: Avenir;
    font-size: 2rem;
    line-height: 2.7rem;
    color: #101010;
    font-weight: 600;
    margin: 0 2.5rem;
  }

  &__logo {
    background: url(../assets/img/logo.svg) left center no-repeat;
    width: 14rem;
    height: 4.329rem;
    margin-right: 5rem;
  }

  &__cart {
    border: 0.1rem solid rgba(0, 167, 93, 0.2);
    box-sizing: border-box;
    border-radius: 3rem;
  }

  &__burger-menu {
    display: none;
  }
}
.cart {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem 2.4rem;

  &__logo {
    width: 2.8rem;
    height: 2.4rem;
    background: url(../assets/img/cart.svg) center center no-repeat;
  }

  &__bage {
  }

  &__text {
    font-family: Avenir;
    font-size: 1.8rem;
    line-height: 2.5rem;
    margin: 0 0.6rem;
    color: #101010;
  }
}
</style>
