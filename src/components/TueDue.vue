<template>
  <div id="todolist">
    <div class="mb-3">
      <label for="formGroupExampleInput" class="form-label"><h2>Tue Due in Vue: </h2></label>
      <input 
        type="text" 
        v-model="newItem"
        @keyup.enter="addItem"
        class="form-control" 
        id="formGroupExampleInput" 
        placeholder=""
      />
      <table
        class="table table-striped">
        <thead>
          <tr>
            <th>Tue Due</th>
            <th>Done!</th>
          </tr>
        </thead>
        <tbody>
          <TueDueItem
            v-for="(item, index) in list" 
            :key="index" 
            :name="item" 
            @delete="removeItem(index)" 
          />
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import TueDueItem from './TueDueItem.vue'

export default {
  name: 'TueDue',
  components: {
    TueDueItem
  },
  data() {
    return {
      list: [
        'sample',
        'thingy'
      ],
      newItem: ''
    }
  },
  methods: {
    addItem() {
      this.list.push(this.newItem)
      this.newItem = ''
    },
    removeItem(index) {
      this.list.splice(index, 1)
    }
  },
}
</script>

<style scoped>
  label {
    font-weight: bold;
  } 
</style>

