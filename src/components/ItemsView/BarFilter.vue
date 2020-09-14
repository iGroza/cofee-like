<template>
  <div class="filter__item">
    <div class="filter__bars">
      <div class="bar">
        <span class="bar__item bar__item_active" v-for="i in max"></span>
      </div>
      <input
        type="range"
        class="filter__input"
        min="1"
        :max="max.length"
        v-model:value="value"
        @change="onChange"
      />
    </div>
    <div class="filter__title">{{this.title}}</div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    id: String
  },

  data() {
    return {
      value: 5,
      max: new Array(5)
    };
  },

  watch: {
    value(value) {
      this.$el.querySelectorAll("span").forEach((span, i) => {
        if (i >= value) {
          span.classList.remove("bar__item_active");
        } else {
          span.classList.add("bar__item_active");
        }
      });
    }
  },

  methods: {
    onChange() {
      this.$emit("change", { value: this.value, id: this.id });
    }
  }
};
</script>

<style lang='scss' scoped>
@media (max-width: 1200px) {
  .filter {
    &__input {
    }
  }
}

.filter {
  &__item {
  }

  &__bars {
    display: flex;
  }

  &__title {
    font-family: Avenir;
    font-size: 1.2rem;
    line-height: 1.6rem;
    color: #101010;
    opacity: 0.5;
    margin-top: 0.8rem;
    width: 10rem;
  }

  &__input {
    position: absolute;
    width: 9.7rem;
    opacity: 0;
    -webkit-appearance: none;
    height: 2rem;
    cursor: pointer;
  }
}
.bar {
  position: absolute;
  display: flex;

  &__item {
    width: 1.7rem;
    height: 0.8rem;
    border-radius: 0.2rem;
    background: #00a75d;
    opacity: 0.2;
    margin: 0 0.15rem;

    &:nth-child(1) {
      margin: 0 0.15rem 0 0;
    }

    &:nth-last-child(1) {
      margin: 0 0 0 0.15rem;
    }

    &_active {
      opacity: 1;
    }
  }
}
</style>