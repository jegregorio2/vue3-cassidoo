<template>
  <div class="counter">
    <h2>Counter: </h2>
      <h3>We are going to count: {{ count }}</h3>
      <button 
        class="btn btn-primary" 
        type="submit"
        @click="add">Click me to up the count!</button>
      <button 
        class="btn btn-primary" 
        type="submit"
        @click="subtract">Click me to sink the count!</button>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
  },
  data() {
    return {
      count: 0
    }
  },
  methods: {
    add() {
      this.count++
    },
    subtract() {
      this.count--
    },
  }
}
</script>

<style scoped>
  .counter {
    padding: 20px;
  }
  .counter button {
    margin-right: 10px;
  }
</style>