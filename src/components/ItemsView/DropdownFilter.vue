<template>
  <div class="dropdown">
      <div class="dropdown__title">{{this.title}}</div>
      <div class="dropdown__input"></div>
      <div class="dropdown__options">
          <div class="dropdown__option-item" v-for="option in options" :id='option.title'>{{option.title}}</div>
      </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    id: String,
    options: Array
  }
};
</script>

<style>
.arrow {
  background: url("data:image/svg+xml;charset=utf-8,%3Csvg width=%2212%22 height=%227%22 viewBox=%220 0 12 7%22 fill=%22none%22 xmlns=%22http://www.w3.org/2000/svg%22 preserveAspectRatio=%22none%22%3E%3Cpath d=%22M1 1l5 5 5-5%22 stroke=%22%2300a75d%22/%3E%3C/svg%3E")
    no-repeat;
}
</style>