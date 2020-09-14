<template>
  <div class="dropdown">
    <div class="dropdown__title">{{this.title}}</div>
    <div class="dropdown__input input" @click="onInputClick">
      <div class="input__title">{{this.selectedOption.title}}</div>
      <div class="input__arrow"></div>
    </div>
    <div class="dropdown__options">
      <div class="options" :class="{'options_active': isShowOptions}">
        <div
          v-if="isShowOptions"
          class="options__item"
          v-for="option in options"
          :id="option.id"
          :class="{'options__item_selected': option.id === selectedOption.id}"
          @click="onItemClick(option)"
        >{{option.title}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    id: String,
    options: Array
  },

  data() {
    return {
      selectedOption: this.options[0],
      isShowOptions: false
    };
  },

  methods: {
    onItemClick(data) {
      this.isShowOptions = false;
      this.selectedOption = data;
      this.$emit("change", { value: data.id, id: this.id });
    },

    onInputClick() {
      this.isShowOptions = !this.isShowOptions;
    }
  }
};
</script>

<style lang='scss'>
.dropdown {
  &__title {
    font-family: Avenir;
    font-size: 1.2rem;
    line-height: 1.6rem;
    color: #101010;
    opacity: 0.5;
  }

  &__input {
    display: flex;
    padding-bottom: 1rem;
    border-bottom: solid 0.1rem #b3e5ce;
    justify-content: space-between;
    align-items: center;
  }

  &__options {
    position: relative;
  }

  .options {
    display: flex;
    position: absolute;
    flex-direction: column;
    z-index: 1;
    background: white;
    width: 100%;
    opacity: 0;

    &_active {
      opacity: 1;
    }

    &__item {
      z-index: 2;
      font-family: Avenir;
      font-size: 1.6rem;
      line-height: 1.5rem;
      color: #101010;
      cursor: pointer;
      width: 100%;
      height: 100%;

      &:hover {
        color: #00a75d;
      }

      &_selected {
        color: #80d3ae;
      }
    }
  }

  .input {
    &__title {
      font-family: Avenir;
      font-size: 1.6rem;
      line-height: 2.2rem;
      color: #101010;
    }

    &__arrow {
      width: 1rem;
      height: 0.5rem;
      background: url("../../assets/img/arrow_down.svg") no-repeat;
    }
  }
}
</style>