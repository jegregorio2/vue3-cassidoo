<template>
  <tr class="todoitem">
    <td>{{ name }}</td>
    <td><button 
      class="btn" 
      type="submit"
      @click="$emit('delete')">Done!</button></td>
  </tr>
</template>

<script>
export default {
  name: 'TueDueItem',
  props: {
    name: String
  }
}
</script>

<style scoped>
  .btn {
    background-color: var(--bs-indigo);
    color: var(--bs-white);
  } 
</style>
