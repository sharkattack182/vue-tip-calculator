<template>
  <div id="app">
    <div class="calculator">
      <div class="display">{{current || "0"}}</div>
      <div class="btn" @click="clear">Clear</div>
      <div class="btn" @click="sign">+/-</div>
      <div class="btn" @click="percent">%</div>
      <div class="btn operator">/</div>
      <div class="btn">7</div>
      <div class="btn">8</div>
      <div class="btn">9</div>
      <div class="btn operator">x</div>
      <div class="btn">4</div>
      <div class="btn">5</div>
      <div class="btn">6</div>
      <div class="btn operator">-</div>
      <div class="btn">1</div>
      <div class="btn">2</div>
      <div class="btn">3</div>
      <div class="btn operator">+</div>
      <div class="zero btn">0</div>
      <div class="btn">.</div>
      <div class="btn operator">=</div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  data () {
    return {
      current: "100"
    }
  },
  methods: {
    clear() {
      this.current = ""
    }, 
    sign() {
      this.current.charAt(0) === "-" ? 
      this.current.clice(1) : `-${this.current}`
    }, 
    percent() {
      this.current = `${parseFloat(this.current) / 100}`
    }
  }
}
</script>

<style>
.calculator {
  display: grid;
  grid-template: repeat(4. 1fr);
  grid-auto-rows: minmax(50px, auto);
  width: 50vw;
  margin: auto
}

.display {
  grid-column: 1/5;
  background-color: #333;
  color: white;
  font-size: 2em;
  text-align: center;
}

.zero {
  grid-column: 1 / 3;
}

.btn {
  background-color: #eee;
  border: 1px solid #333;
  text-align: center;
  font-size: 2em;
}

.operator {
  background-color: orange;
  color: white
}
</style>
