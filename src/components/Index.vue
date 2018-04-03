<template>
  <div class="app-container yyy">
    <h1>Оформление заказа</h1>
    <div class="ordering">
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
      <app-ordering-right-panel/>
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
  .app-container{
    width: 600px;
    margin: 0 auto;
  }
  .ordering{
    display: flex;
  }
  .ordering-left-panel{
    width: 30%;
  }
  .ordering-left-panel{
    width: 30%;
  }
</style>
