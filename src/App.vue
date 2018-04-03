<template>
  <div id="app">
    <!--<router-view/>-->
    <app-index></app-index>
  </div>
</template>

<script>
import index from './components/Index'
export default {
  name: 'App',
  components: {
    'app-index': index
  }
}
</script>

<style lang="scss">

.yyy *{
  outline: 1px solid red;
}

@import "assets/scss/variables";
@import "assets/scss/reboot";

</style>
