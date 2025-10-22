<script>
export default {
  data() {
    return {
      x: 0,
      y: 0,
      operators: ["+", "-", "*", "/", "%"],
      selectedOp: ""
    }
  },
  computed: {
    result() {
      let total = 0
      const { x, y, selectedOp } = this
      switch (selectedOp) {
        case "+": total = x + y; break
        case "-": total = x - y; break
        case "*": total = x * y; break
        case "/": total = y !== 0 ? x / y : "Error"; break
        case "%": total = y !== 0 ? x % y : "Error"; break
      }
      return total
    }
  }
}
</script>
<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" :key="op" :value="op">{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>
    <p>= {{result}}</p>
</template>
<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }
</style>