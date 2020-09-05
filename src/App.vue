<template>
  <div class="view-body">
    <ItemsView />
  </div>
</template>

<script>
import ItemsView from "@/views/ItemsView.vue";

export default {
  components: {
    ItemsView
  }
};
</script>

<style lang="scss">
html {
  font-size: 62.5%;
}

.view-body {
  margin: 2.4rem 14rem;
}

@media (max-width: 1200px) {
  .view-body {
    margin: 1.6rem 1.8rem;
  }
}
</style>
