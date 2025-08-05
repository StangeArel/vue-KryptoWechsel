<template>
  <input
    min="0"
    type="number"
    @input="changeAmount($event.target.value)"
    placeholder="Bitte eine Zahl eingeben …"
  />
</template>

<script>
export default {
  props: {
    changeAmount: {
      type: Function,
      required: true,
    },
  },
}
</script>

<style scoped>
input {
  border-radius: 3px;
  border: 0;
  padding: 20px 25px;
  background: #fafafa;
  color: #333;
  outline: none;
  width: 500px;
  position: relative;
  top: -20px;
  font-size: 1.2em;
  margin: 10px;
}
</style>
