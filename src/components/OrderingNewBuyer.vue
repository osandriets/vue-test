<template>
  <form class="">
    <div>
      <p>Получатель заказа</p>
      <div>
        <label>Имя и фамилия</label>
        <input>
      </div>
      <div>
        <label>Телефон</label>
        <input>
      </div>
      <div>
        <label >Город</label>
        <input value="Киев">
      </div>
      <div>
        <label >Эл. почта</label>
        <input placeholder="user@mail.com">
      </div>
      <div>
        <a v-if="add_comments" @click="add_comments = false">Добавить комментарий к заказу</a>
        <textarea v-else></textarea>
      </div>
    </div>
    <div>
      <div>
        <label>Доставка</label>
        <select v-model="delivery">
          <option>«Новая почта» — 25 грн.</option>
          <option>А</option>
          <option>Б</option>
          <option>В</option>
        </select>
      </div>
      <div>
        <label>Адрес склада</label>
        <select v-model="warehouse_address">
          <option>Львов, Отделение №8 (до 30 кг): ул. Гетьмана И. Мазепы, 37</option>
          <option>А</option>
          <option>Б</option>
          <option>В</option>
        </select>
      </div>
    </div>
    <div>
      <div>
        <label>Оплата</label>
        <select v-model="payment">
          <option>наложеный платёж</option>
          <option>А</option>
          <option>Б</option>
          <option>В</option>
        </select>
      </div>
    </div>
    <div>
      <div>
        <label></label>
        <button>Оформить заказ</button>
      </div>
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

</style>
