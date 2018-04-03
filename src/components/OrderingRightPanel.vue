<template>
    <div class="">
        <div>
            <div v-for="item in contacts" v-bind:key="item.id">
                <a href="item.url">{{item.name}}</a>
                <p>{{item.price}} грн. x {{item.quantity}} шт.</p>
                <p>{{item.price * item.quantity}} грн.</p>
            </div>
        </div>
        <div>{{ reversedMessage }}</div>
    </div>
</template>
<script>
export default {
  data () {
    return {
      contacts: [
        {
          url_img: false,
          name: 'Цифровий фотоапарат Nikon D5100 kit (18-55 VR)',
          url: '#',
          price: 6568,
          quantity: 1
        },
        {
          url_img: false,
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
