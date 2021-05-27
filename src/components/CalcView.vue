<template>
  <div class="calculator">
    <div class="result"></div>

    <div class="pad">
      <button class="clear">C</button>
      <button>/</button>
      <button>7</button>
      <button>8</button>
      <button>9</button>
      <button>x</button>
      <button>4</button>
      <button>5</button>
      <button>6</button>
      <button>-</button>
      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button>+</button>
      <button class="zero">0</button>
      <button class="equal">=</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
