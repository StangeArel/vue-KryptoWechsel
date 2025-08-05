<template>
  <h1>vue-KryptoWechsel</h1>
  <Input :changeAmount="changeAmount" />
  <!-- {{ cryptoFirst }} -->
  <!-- {{ cryptoSecond }} -->
  <!-- {{ amount }} -->
  <div className="selectors">
    <Selector :setCrypto="setCryptoFirst" />
    <Selector :setCrypto="setCryptoSecond" />
  </div>
</template>

<script>
import Input from './components/Input.vue'
import Selector from './components/Selector.vue'

export default {
  components: { Input, Selector },

  data() {
    return {
      amount: 0,
      cryptoFirst: '',
      cryptoSecond: '',
    }
  },

  methods: {
    changeAmount(val) {
      this.amount = val
    },
    setCryptoFirst(val) {
      this.cryptoFirst = val
    },
    setCryptoSecond(val) {
      this.cryptoSecond = val
    },
  },
}
</script>

<style scoped>
.selectors {
  display: flex;
  justify-content: space-around;
  width: 700px;
  margin: 0 auto;
}
</style>
