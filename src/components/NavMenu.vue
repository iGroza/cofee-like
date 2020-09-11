<template>
  <div class="nav">
    <div class="nav__menu">
      <div class="nav__logo"></div>
      <div class="nav__item">Кофе</div>
      <div class="nav__item">Аксессуары</div>
    </div>
    <div class="nav__cart">
      <div class="cart">
        <div class="cart__icon">
          <div class="cart__bage">0</div>
        </div>
        <div class="cart__text">{{prettifiedOrderCost}} ₽</div>
      </div>
      <div class="nav__burger-menu"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      orderCost: 5223
    };
  },

  computed: {
    prettifiedOrderCost() {
      return this.orderCost
        .toString()
        .replace(/,/g, "")
        .replace(/\B(?=(\d{3})+(?!\d))/g, " ");
    }
  }
};
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
      margin: 3.7rem 3.5rem 0.3rem 0 !important;
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

    &__bage {
      width: 1.6rem !important;
      height: 1.6rem !important;
      font-size: 0.9rem !important;
      line-height: 1.2rem !important;
    }
  }
}

.nav {
  display: flex;
  display: 100%;
  justify-content: space-between;
  align-items: flex-start;
  &__menu {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
  }

  &__item {
    font-family: Avenir;
    display: flex;
    font-size: 2rem;
    line-height: 2.7rem;
    color: #101010;
    font-weight: 600;
    margin: 0 2.5rem 0.2rem 2.5rem;
    border-bottom: solid 0.2rem rgba(0, 167, 93, 0.2);
  }

  &__logo {
    background: url(../assets/img/logo.svg) left center no-repeat;
    width: 14rem;
    height: 4.329rem;
    margin-right: 4.5rem;
    margin-top: 1rem;
  }

  &__cart {
    display: flex;
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
  border: 0.1rem solid rgba(0, 167, 93, 0.2);
  box-sizing: border-box;
  border-radius: 3rem;

  &__icon {
    width: 2.8rem;
    height: 2.4rem;
    background: url(../assets/img/cart.svg) center center no-repeat;
  }

  &__bage {
    display: flex;
    justify-content: center;
    position: absolute;
    width: 2rem;
    height: 2rem;
    background: linear-gradient(180deg, #45cd91 0%, #00a75d 100%);
    font-family: Avenir;
    font-size: 1.2rem;
    line-height: 1.6rem;
    color: #ffffff;
    border-radius: 10rem;
    align-items: center;
    margin: -0.65rem 0 0rem 1.6rem;
  }

  &__text {
    font-family: Avenir;
    font-size: 1.8rem;
    line-height: 2.5rem;
    margin: 0 0.6rem 0 1.6rem;
    color: #101010;
  }
}
</style>
