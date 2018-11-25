<template>
  <div class="home container">
    <div class="row">
      <div class="col s12 m4 l4" v-for="(phone, i) in phones" :key="i">
        <div class="card">
          <div class="card-image">
            <img v-bind:src="require(`@/assets/${phone.img}`)">
          </div>
          <div class="card-content">
            <span class="card-title">{{phone.name}}</span>
            <p>{{phone.description}}</p>
          </div>
          <div class="card-action">
            <a href="#" v-on:click="addToCart($event, phone)">Adicionar ao carrinho R${{phone.cost}}</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
  data: () => ({
    phones: [
      {
        name: 'iPhone 8',
        description: '64GB Cinza Espacial Tela 4.7" IOS 4G Câmera 12MP - Apple',
        img: '1.jpeg',
        cost: 2000
      }, {
        name: 'Motorola Moto G5s',
        description: 'Dual Sim 32gb 5.2',
        img: '2.jpeg',
        cost: 1200
      }, {
        name: 'Celular Motorola C',
        description: '2017 Xt1754 Dual 16gb 5.0 Moto C',
        img: '3.jpeg',
        cost: 1100
      }, {
        name: 'Samsung Galaxy J5',
        description: 'Dual Chip Android 7.0 Tela 5,2" Octa-Core 1.6 GHz 32GB 4G Câmera 13MP - Dourado',
        img: '4.jpeg',
        cost: 900
      }, {
        name: 'J1 Mini',
        description: 'Prime Dual 3g Preto',
        img: '5.jpeg',
        cost: 400
      }, {
        name: 'iPhone 7 Plus',
        description: '32GB Ouro Rosa Tela Retina HD 5,5" 3D Touch Câmera Dupla de 12MP - Apple',
        img: '6.jpeg',
        cost: 200
      }, {
        name: 'iPhone 7 Plus',
        description: '32GB Preto Matte Tela Retina HD 5,5" 3D Touch Câmera Dupla de 12MP - Apple',
        img: '7.jpeg',
        cost: 2200
      }, {
        name: 'Smartphone LG Q6',
        description: 'Plus Dual Chip Android 7.0 Tela 5.5" Full Hd+ Snapdragon MSM8940 64GB 4G Câmera 13MP - Platinum',
        img: '8.jpeg',
        cost: 900
      }, {
        name: 'Smartphone Samsung Galaxy S8',
        description: 'Dual Chip Android 7.0 Tela 5.8" Octa-Core 2.3GHz 64GB 4G Câmera 12MP - Preto',
        img: '9.jpeg',
        cost: 2800
      }, {
        name: 'Smartphone Samsung Galaxy J8',
        description: '64GB Dual Chip Android 8.0 Tela 6" Octa-Core 1.8GHz 4G Câmera 16MP F1.7 + 5MP F1.9 (Dual Cam) - Preto',
        img: '10.jpeg',
        cost: 2400
      }, {
        name: 'Smartphone Samsung Galaxy J7',
        description: 'Pro Android 7.0 Tela 5.5" Octa-Core 64GB 4G Wi-Fi Câmera 13MP - Preto',
        img: '11.jpeg',
        cost: 1900
      }, {
        name: 'Smartphone Samsung Galaxy J8',
        description: '64GB Dual Chip Android 8.0 Tela 6" Octa-Core 1.8GHz 4G Câmera 16MP F1.7 + 5MP F1.9 (Dual Cam) - Prata',
        img: '12.jpeg',
        cost: 2400
      }, 
    ]
  }),
  methods: {
    addToCart(e, phone) {
      e.preventDefault()
      const cart = JSON.parse(localStorage.getItem('cart')) || []
      cart.push(phone)
      localStorage.setItem('cart', JSON.stringify(cart))
    }
  }
}
</script>
