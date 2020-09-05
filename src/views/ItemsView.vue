<template>
  <div class="items-view">
    <Header />
    <hr class="hr_separator" />
    <NavMenu />
    <ItemsList />
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import NavMenu from "@/components/NavMenu.vue";
import ItemsList from "@/components/ItemsView/ItemsList.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Header,
    NavMenu,
    ItemsList,
    Footer
  }
};
</script>

<style lang="scss">
.hr_separator {
  width: 100%;
  background: #101010;
  opacity: 0.1;
  margin: 2.4rem 0 3.3rem 0;
}

@media (max-width: 1200px) {
  .hr_separator  {
    display: none;
  }
}
</style>
