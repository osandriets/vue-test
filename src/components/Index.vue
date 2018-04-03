<template>
  <div class="app-container yyy1">
    <div class="ordering">
      <h1 class="ordering__title">Оформление заказа</h1>
      <div class="ordering-left-panel">
          <div class="ordering-left-panel__block_button">
              <button class="ordering-left-panel__button"
                      :class="{active: selectedComponent == 'app-ordering-new-buyer'}"
                      @click="selectedComponent = 'app-ordering-new-buyer'"
              >
                  <span>Я новый <br>покупатель</span>
              </button>
              <button class="ordering-left-panel__button"
                      :class="{active: selectedComponent == 'app-ordering-registered-buyer'}"
                      @click="selectedComponent = 'app-ordering-registered-buyer'"
              >
                  <span>Я зарегистрированный <br> покупатель</span>
              </button>
          </div>
          <keep-alive>
            <component class="ordering-left-panel__body" :is="selectedComponent"></component>
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
    font-size: $h1-font-size;
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
  .ordering-left-panel__block_button{
      display: flex;
      margin-bottom: -$border-width;
  }
  .ordering-left-panel__button{
      background: transparent;
      border: $border-width solid $border-color;
      font-weight: bold;
      text-align: left;
      padding: map-get($spacers, 2) map-get($spacers, 3);
      outline: none;

      &:hover{
          span{
              border-bottom: $border-width dotted transparent;
          }
      }
      &:not(.active){
        cursor: pointer;
        color: $link-color;
          span{
              border-bottom: $border-width dotted $link-color;
          }
      }
      &.active{
          background: $inverse-color;
          border-bottom: $border-width inset $inverse-color;
          span{
              border-bottom: $border-width dotted transparent;
          }
      }
      & + & {
          margin-left: -$border-width;
      }
      &:first-child{
          border-top-left-radius: $border-radius-base;
      }
      &:last-child{
          border-top-right-radius: $border-radius-base;
      }
  }

  .ordering-left-panel__body{
      background: $inverse-color;
      border: $border-width solid $border-color;
      border-radius: 0 $border-radius-base $border-radius-base $border-radius-base;
  }
</style>
