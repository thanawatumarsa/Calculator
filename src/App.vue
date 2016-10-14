<template lang="html">
  <div id="app">
    <button @click="addNumber('0')">0</button>
    <button @click="addNumber('1')">1</button>
    <button @click="addNumber('2')">2</button>
    <button @click="addNumber('3')">3</button>
    <button @click="addNumber('4')">4</button>
    <button @click="addNumber('5')">5</button>
    <button @click="addNumber('6')">6</button>
    <button @click="addNumber('7')">7</button>
    <button @click="addNumber('8')">8</button>
    <button @click="addNumber('9')">9</button>
    <button @click="operation('+')">+</button>
    <button @click="operation('-')">-</button>
    <button @click="operation('*')">*</button>
    <button @click="operation('/')">/</button>
    <button @click="calculate()">=</button>
    <button @click="clear('c')">c</button>

    {{ num1 }}
    {{ operator }}
    {{ num2 }}
    {{ sum }}
  </div>
</template>

<script>
export default {
  data () {
    return {
      num1: '',
      num2: '',
      operator: '',
      sum: ''
    }
  },
  computed: {},
  mounted () {},
  methods: {
    addNumber (number) {
      var zero
      if (this.operator === '') {
        zero = this.num1
        zero += number
        zero = parseInt(zero)
        this.num1 = zero
        console.log(this.num1)
      } else {
        zero = this.num2
        zero += number
        zero = parseInt(zero)
        this.num2 = zero
        console.log(this.num2)
      }
    },
    operation (Opr) {
      this.operator = Opr
    },
    calculate () {
      if (this.operator === '+') {
        this.sum = parseInt(this.num1) + parseInt(this.num2)
        this.sum = '= ' + this.sum
      } else if (this.operator === '-') {
        this.sum = parseInt(this.num1) - parseInt(this.num2)
        this.sum = '= ' + this.sum
      } else if (this.operator === '*') {
        this.sum = parseInt(this.num1) * parseInt(this.num2)
        this.sum = '= ' + this.sum
      } else if (this.operator === '/') {
        this.sum = parseInt(this.num1) / parseInt(this.num2)
        this.sum = '= ' + this.sum
      } else {
        this.sum = 'ERROR'
      }
    },
    clear () {
      this.num1 = ''
      this.num2 = ''
      this.operator = ''
      this.sum = ''
    }
  },
  components: {}
}
</script>

<style lang="css">
</style>
