<template>
    <h1>vue-KryptoWechsel</h1>
    <Input :changeAmount="changeAmount" :convert="convert" />
    <p className="error" v-if="error != ''">
        <b
            ><u>{{ error }}</u></b
        >
    </p>
    <p className="result" v-if="result != 0">{{ result }}</p>
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
    import CryptoConvert from 'crypto-convert'

    const convert = new CryptoConvert()

    export default {
        components: { Input, Selector },

        data() {
            return {
                amount: 0,
                cryptoFirst: '',
                cryptoSecond: '',
                error: '',
                result: 0,
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
            async convert() {
                if (this.amount <= 0) {
                    this.error = 'Bitte geben Sie eine Zahl größer als 0 ein ❌'
                    return
                } else if (this.cryptoFirst == '' || this.cryptoSecond == '') {
                    this.error = 'Wählen Sie irgend eine Währung ⚛️'
                    return
                } else if (this.cryptoFirst == this.cryptoSecond) {
                    this.error = 'Wählen Sie eine andere Währung ↔️'
                    return
                }
                this.error = ''

                await convert.ready()
                if (this.cryptoFirst === 'BTC' && this.cryptoSecond == 'ETH') {
                    this.result = convert.BTC.ETH(this.amount)
                } else if (
                    this.cryptoFirst === 'BTC' &&
                    this.cryptoSecond == 'USDT'
                ) {
                    this.result = convert.BTC.USDT(this.amount)
                } else if (
                    this.cryptoFirst === 'ETH' &&
                    this.cryptoSecond == 'BTC'
                ) {
                    this.result = convert.ETH.BTC(this.amount)
                } else if (
                    this.cryptoFirst === 'ETH' &&
                    this.cryptoSecond == 'USDT'
                ) {
                    this.result = convert.ETH.USDT(this.amount)
                } else if (
                    this.cryptoFirst === 'USDT' &&
                    this.cryptoSecond == 'BTC'
                ) {
                    this.result = convert.USDT.BTC(this.amount)
                } else if (
                    this.cryptoFirst === 'USDT' &&
                    this.cryptoSecond == 'ETH'
                ) {
                    this.result = convert.USDT.ETH(this.amount)
                }
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

    .error {
        color: #eaff00;
        font-size: 1.2em;
        text-align: center;
        margin-top: 20px;
    }

    .result {
        color: #00eaff;
        font-size: 2em;
        text-align: center;
        margin-top: 20px;
        font-family: 'Nabla', cursive;
    }
</style>
