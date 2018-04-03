<template>
  <div class="app-container yyy">
    <div class="ordering">
      <h1 class="ordering__title">Оформление заказа</h1>
      <div class="ordering-left-panel">
          <button class="btn btn-primary"
                  :class="{active: selectedComponent == 'app-ordering-new-buyer'}"
                  @click="selectedComponent = 'app-ordering-new-buyer'"
          >
            Я новый покупатель
          </button>
          <button class="btn btn-success"
                  :class="{active: selectedComponent == 'app-ordering-registered-buyer'}"
                  @click="selectedComponent = 'app-ordering-registered-buyer'"
          >
            Я зарегистрированный покупатель
          </button>
          <keep-alive>
            <component :is="selectedComponent"></component>
          </keep-alive>
      </div>
      <app-ordering-right-panel class="ordering-right-panel"/>
    </div>
  </div>
</template>

<script>

import OrderingNewBuyer from './OrderingNewBuyer.vue'
import OrderingRegisteredBuyer from './OrderingRegisteredBuyer.vue'
import OrderingRightPanel from './OrderingRightPanel'

export default {
  data () {
    return {selectedComponent: 'app-ordering-new-buyer'
    }
  },
  components: {
    'app-ordering-new-buyer': OrderingNewBuyer,
    'app-ordering-registered-buyer': OrderingRegisteredBuyer,
    'app-ordering-right-panel': OrderingRightPanel
  }
}
</script>

<style scoped lang="scss">
  @import "../assets/scss/variables";
  .app-container{
    width: 100%;
    min-width: $min-width;
    max-width: $max-width;
    padding-left: $grid-gutter-width/2;
    padding-right: $grid-gutter-width/2;
    margin-left: auto;
    margin-right: auto;
  }
  .ordering{
    display: flex;
    flex-wrap: wrap;
  }
  .ordering__title{
    width: 100%;
    padding-left: $grid-gutter-width/2;
    padding-right: $grid-gutter-width/2;
    font-size: 32px;
  }
  .ordering-left-panel{
    width: 100%;
    padding-left: $grid-gutter-width/2;
    padding-right: $grid-gutter-width/2;
    @media screen and(min-width: map-get($breakpoints, m)) {
      width: 100% * 2 / 3;
    }
  }
  .ordering-right-panel{
    width: 100%;
    padding-left: $grid-gutter-width/2;
    padding-right: $grid-gutter-width/2;
    @media screen and(min-width: map-get($breakpoints, m)) {
      width: 100% * 1 / 3;
    }
  }
</style>
