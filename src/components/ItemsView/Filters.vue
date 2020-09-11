<template>
  <div class="filters__list">
    <DropdownFilter
      class="filters__item"
      v-for="filter in dropdownFilter"
      :title="filter.title"
      :id="filter.id"
      :options="filter.options"
      @change="onChange"
    />
      <BarFilter
      class="filters__item"
      v-for="filter in barFilters"
      :title="filter.title"
      :id="filter.id"
      @change="onChange"
    />
  </div>
</template>

<script>
import BarFilter from "./BarFilter.vue";
import DropdownFilter from "./DropdownFilter.vue";

export default {
  data() {
    return {
      dropdownFilter:[
        {
          title: 'Бренд',
          id: ' brand',
          options:[
            {
              title:'Выберите брэнд',
              id: 'chooseBrand'
            },

            {
              title:'Cofee Like',
              id: 'cofeeLike'
            }
          ]
        },

       {
          title: 'Фасовка',
          id: 'sort',
          options:[
            {
              title:'Любая',
              id: 'all'
            },

            {
              title:'250г',
              id: '250gramm'
            }
          ]
        }
      ],

      barFilters: [
        {
          title: "Плотность",
          id: "density"
        },

        {
          title: "Крепость",
          id: "hardiness"
        },

        {
          title: "Сладкость",
          id: "sweetness"
        },

        {
          title: "Горечь",
          id: "bitterness"
        },

        {
          title: "Кислотность",
          id: "acidity"
        },

        {
          title: "Аромат",
          id: "flavor"
        }
      ]
    };
  },

  components: {
    BarFilter,
    DropdownFilter
  },

  methods: {
    onChange({ id, value }) {
      console.log({ id, value });
    }
  }
};
</script>

<style lang="scss">
@media (max-width: 1200px) {
  .filters {
    &__item {
          flex: 0 0 50% !important;
    }
  }
}

.filters {
  &__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
  }

  &__item {
    flex: 0 0 33.333%;
    // margin-right: 2rem;
  }
}
</style>
