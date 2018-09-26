<template>
  <div class="Apps">

    <h1>Hello, this is the crypto-currency page</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna ali...</p>

    <div id="crypto-container" v-for="(value, key) in cryptos">
      <span class="left">{{ key }}</span>
      <span class="right">${{ value.USD }}</span>
    </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "Apps",
  data: () => ({
    cryptos: [], 
    errors: []
  }),

  created () {
    axios.get('https://min-api.cryptocompare.com/data/pricemulti?fsyms=BTC,ETH,IOT&tsyms=USD')
      .then(response => {
        this.cryptos = response.data
        console.log(response)         // This will give you access to the full object
      })
      .catch(e => {
        this.errors.push(e)
      })
  }
};
</script>

<style>

  div#crypto-container {
    background:white;
    width: 100%;
    margin: 0 auto 4px auto;
    padding: 1em;
    box-shadow: 10px 10px 0 lightgrey;
  }

  span.left {
    font-weight: bold;
  }

  span.right {
    float:right;
  }
</style>