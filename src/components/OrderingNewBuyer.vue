<template>
  <form class="">
    <div class="ordering-left-panel__body_line">
      <p class="ordering-left-panel__line_header">Получатель заказа</p>
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__label">Имя и фамилия</label>
        <input class="ordering-left-panel__input">
      </div>
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__label">Телефон</label>
        <input class="ordering-left-panel__input">
      </div>
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__label">Город</label>
        <input class="ordering-left-panel__input" value="Киев">
      </div>
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__label">Эл. почта</label>
        <input class="ordering-left-panel__input" placeholder="user@mail.com">
      </div>
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__label">&nbsp;</label>
        <a v-if="add_comments" @click="add_comments = false">Добавить комментарий к заказу</a>
        <textarea class="ordering-left-panel__input" v-else></textarea>
      </div>
    </div>
    <div class="ordering-left-panel__body_line">
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__h6">Доставка</label>
        <select class="ordering-left-panel__input" v-model="delivery">
          <option>«Новая почта» — 25 грн.</option>
          <option>А</option>
          <option>Б</option>
          <option>В</option>
        </select>
      </div>
      <div class="ordering-left-panel__form_group">
        <label class="ordering-left-panel__label">Адрес склада</label>
        <select class="ordering-left-panel__input_md" v-model="warehouse_address">
          <option>Львов, Отделение №8 (до 30 кг): ул. Гетьмана И. Мазепы, 37</option>
          <option>А</option>
          <option>Б</option>
          <option>В</option>
        </select>
      </div>
    </div>
    <div class="ordering-left-panel__body_line">
      <div class="ordering-left-panel__form_group">
        <label  class="ordering-left-panel__h6">Оплата</label>
        <select class="ordering-left-panel__input" v-model="payment">
          <option>наложеный платёж</option>
          <option>А</option>
          <option>Б</option>
          <option>В</option>
        </select>
      </div>
    </div>
    <div class="ordering-left-panel__footer">
        <button class="ordering-left-panel__button">Оформить заказ</button>
    </div>
  </form>
</template>

<script>
export default {
  data () {
    return {
      add_comments: true,
      delivery: '«Новая почта» — 25 грн.',
      warehouse_address: 'Львов, Отделение №8 (до 30 кг): ул. Гетьмана И. Мазепы, 37',
      payment: 'наложеный платёж'
    }
  }
}
</script>

<style scoped lang="scss">
    @import "../assets/scss/variables";
    @import "../assets/scss/buttons";
    @import "../assets/scss/forms";

    $label-width: 9.5rem;

    .ordering-left-panel__body_line{
        padding: map-get($spacers, 3) map-get($spacers, 3);
        border-bottom: $border-width dotted $border-color;
        //display: flex;
    }
    .ordering-left-panel__line_header{
        font-size: $font-size-lg;
        font-weight: bold;
    }
    .ordering-left-panel__h6{
        width: $label-width;
        font-size: $font-size-lg;
        font-weight: bold;
        margin-bottom: 0;
    }
    .ordering-left-panel__label{
        width: $label-width;
        color: $text-muted;
        font-size: $font-size-md;
        margin-bottom: 0;
    }
    .ordering-left-panel__form_group{
        display: flex;
        justify-content: flex-start;
        &:not(:last-child){
            margin-bottom: map-get($spacers, 3);
        }
    }
    .ordering-left-panel__input{
        @extend .form-control;
        width: 22rem;
    }
    .ordering-left-panel__input_md{
        @extend .form-control;
        width: 38rem;
    }
    .ordering-left-panel__footer{
        padding: map-get($spacers, 3) map-get($spacers, 3);
    }
    .ordering-left-panel__button{
        margin-left: $label-width;
        @extend .btn;
        background:  linear-gradient(to bottom, rgba(0,0,0,0) 0%, rgba(0,0,0,.25) 100%), $primary-color;
        box-shadow: inset 0px -1px 5px 0px rgba(0,0,0,0.75);
        color: $inverse-color;
        font-weight: bold;
        font-size: 20px;
        border-radius: $border-radius-md;
        &:hover{
            background:  linear-gradient(to bottom, rgba(0,0,0,0) 0%, rgba(0,0,0,0) 100%), $primary-dark-color;
        }
        &:focus{
            background:  linear-gradient(to bottom, rgba(0,0,0,0) 0%, rgba(0,0,0,.125) 100%), $primary-dark-color;
        }
    }
</style>
