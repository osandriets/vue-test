<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss">

.yyy *{
  outline: 1px solid red;
}

@import "assets/scss/variables";
@import "assets/scss/mixins";

@import "assets/scss/reboot";
@import "assets/scss/grid";

@import "assets/scss/buttons";
@import "assets/scss/forms";

</style>
