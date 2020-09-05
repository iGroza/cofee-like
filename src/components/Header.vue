<template>
  <div class="header">
    <div class="header__block">
      <div class="header__text">О компании</div>
      <div class="header__text">Доставка</div>
      <div class="header__text">Гарантия качества</div>
      <div class="header__text">Оптовикам</div>
    </div>
    <div class="header__block">
      <div class="header__text header__text_bold">8 800 333 41 30</div>
      <div class="header__text">Заказать звонок</div>
      <div class="header__text">Контакты</div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@media (max-width: 1200px) {
  .header{
    display: none !important;
  }
}

.header {
  display: flex;
  width: 100%;
  justify-content: space-between;

  &__block {
    display: flex;
    justify-content: space-between;
    
    &>:nth-child(1){
      margin-left: 0;
    }

    &>:nth-last-child(1){
      margin-right: 0;
    }
  }

  &__text {
    font-family: Avenir;
    font-size: 1.4rem;
    line-height: 1.9rem;
    color: #101010;
    width: auto;
    opacity: 0.5;
    margin: 0 2rem;

    &_bold {
      opacity: 1;
    }
  }
}
</style>
