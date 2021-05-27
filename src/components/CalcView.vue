<template>
  <div class="calculator">
    <div class="result"> {{ valueDisplayed }} </div>

    <div class="pad">
      <button class="clear" @click="clear">C</button>
      <button @click="handleOp('/')">/</button>
      <button @click="handleDigit(7)">7</button>
      <button @click="handleDigit(8)">8</button>
      <button @click="handleDigit(9)">9</button>
      <button @click="handleOp('x')">x</button>
      <button @click="handleDigit(4)">4</button>
      <button @click="handleDigit(5)">5</button>
      <button @click="handleDigit(6)">6</button>
      <button @click="handleOp('-')">-</button>
      <button @click="handleDigit(1)">1</button>
      <button @click="handleDigit(2)">2</button>
      <button @click="handleDigit(3)">3</button>
      <button @click="handleOp('+')">+</button>
      <button class="zero" @click="handleDigit(0)">0</button>
      <button class="equal" @click="handleOp('=')">=</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalcView',

  data: () => ({
    currentValue: 0,
    savedValue: null,
    currentOp: false
  }),

  methods: {
    clear () {
      this.currentValue = 0
      this.savedValue = null
      this.currentOp = false
    },
    handleDigit (digit) {
      this.currentValue = this.currentValue * 10 + digit
    },
    handleOp (op) {
      if (this.currentOp && this.currentValue) {
        this.process()
      } else {
        this.savedValue = this.currentValue
      }

      this.currentValue = 0
      this.currentOp = op
    },
    process () {
      if (this.currentOp === '+') {
        this.savedValue += this.currentValue
      } else if (this.currentOp === '-') {
        this.savedValue -= this.currentValue
      } else if (this.currentOp === 'x') {
        this.savedValue *= this.currentValue
      } else if (this.currentOp === '/') {
        this.savedValue /= this.currentValue
      } else if (this.currentOp === '=' && this.currentValue) {
        this.savedValue = this.currentValue
      }
      this.currentValue = 0
      this.currentOp = false
    }
  },
  computed: {
    valueDisplayed () {
      if (this.savedValue) {
        return this.currentValue ? this.currentValue : this.savedValue
      } else {
        return this.currentValue
      }
    }
  }
}
</script>

<style scoped>
.calculator {
  --border-style: 2px solid black;
  --border-radius: 4px;

  border: var(--border-style);
  border-radius: var(--border-radius);
  max-width: 350px;
}

.result {
  font-size: 42px;
  width: 100%;
  height: 70px;
  box-sizing: border-box;
  display: grid;
  padding: 10px;
  justify-items: end;
  align-items: center;
  border-bottom: var(--border-radius);
}

.pad {
  display: grid;
  grid-template-columns: repeat(4, minmax(60px, 1fr));
  grid-gap: 10px;
  padding: 15px;
}

button {
  cursor: pointer;
  font-size: 20px;
  display: grid;
  padding: 15px 10px;
  justify-items: center;
  align-items: center;
  border: var(--border-style);
  border-radius: var(--border-radius);
  background: lightgray;
}

.clear {
  background: lightblue;
  grid-column: 1/4;
}

.zero {
  grid-column: 1/4;
}

.equal {
  background: lightgreen;
}
</style>
