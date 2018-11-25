<template>
  <div class="cart container">
    <h1>Carrinho</h1>
    <div class="row">
      <div class="col s12 m4 l4" v-for="(phone, i) in cart" :key="i">
        <div class="card">
          <div class="card-image">
            <img v-bind:src="require(`@/assets/${phone.img}`)">
          </div>
          <div class="card-content">
            <span class="card-title">{{phone.name}}</span>
            <p>{{phone.description}}</p>
          </div>
          <div class="card-action">
            <a href="#" v-on:click="removeFromCart($event, phone)">(R${{phone.cost}}) Remover do carrinho</a>
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    cart: JSON.parse(localStorage.getItem('cart'))
  }),
  methods: {
    removeFromCart(e, phone) {
      e.preventDefault()
      const index = this.cart.indexOf(phone)
      this.cart.splice(index, 1)
      localStorage.setItem('cart', JSON.stringify(this.cart))
    }
  }
}
</script>
