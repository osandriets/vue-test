<template>
    <div>
        <div class="order-card">
            <div class="order-card__header">Ваш заказ</div>
            <div class="order-card__line" v-for="item in contacts" v-bind:key="item.id">
                <div class="order-card__block_img">
                    <img class="order-card__img" :src="item.url_img"/>
                </div>
                <div class="order-card__text">
                    <p>
                        <a href="item.url">{{item.name}}</a>
                    </p>
                    <div class="order-card__block_price">
                        <div class="order-card__text_price">{{item.price}} грн. x {{item.quantity}} шт.</div>
                        <div class="order-card__text_total">{{item.price * item.quantity}} грн.</div>
                    </div>
                </div>
            </div>
            <div class="order-card__footer">{{ reversedMessage }} грн.</div>
        </div>
    </div>
</template>
<script>
export default {
  data () {
    return {
      contacts: [
        {
          url_img: 'static/img1.png',
          name: 'Цифровий фотоапарат Nikon D5100 kit (18-55 VR)',
          url: '#',
          price: 6568,
          quantity: 1
        },
        {
          url_img: 'static/img2.png',
          name: 'MP3-плеер Apple iPod Touch 5Gen 32Gb blue',
          url: '#',
          price: 3689,
          quantity: 1
        }
      ]
    }
  },
  computed: {
    reversedMessage: function () {
      let total = 0
      for (let i = 0; i < this.contacts.length; i++) {
        total += this.contacts[i].price * this.contacts[i].quantity
      }
      return total
    }
  }
}
</script>
<style scoped lang="scss">
    @import "../assets/scss/variables";
    .order-card{
        background: $inverse-color;
        border: 1px solid $border-color;
        border-radius: $border-radius-base;
        font-size: 14px;
    }
    .order-card__header{
        font-size: 18px;
        font-weight: bold;
        border-bottom: $border-width dotted $border-color;
        padding: map-get($spacers, 3) map-get($spacers, 3);
    }
    .order-card__line{
        padding: map-get($spacers, 3) map-get($spacers, 3);
        border-bottom: $border-width dotted $border-color;
        display: flex;
    }
    .order-card__block_img{
        width: 68px;
        height: 68px;
        margin-right: map-get($spacers, 2);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .order-card__img{
        max-width: 100%;
        max-height: 100%;
    }
    .order-card__text{
        flex: 1;
    }
    .order-card__block_price{
        display: flex;
        justify-content: space-between;
    }
    .order-card__text_price{
        color: $text-muted;
    }
    .order-card__text_total{
        font-weight: bold;
    }

    .order-card__footer{
        font-size: 18px;
        font-weight: bold;
        text-align: right;
        padding: map-get($spacers, 3) map-get($spacers, 3);
    }
</style>
