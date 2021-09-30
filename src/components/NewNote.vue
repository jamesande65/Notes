<template>
  <!-- new note -->
  <div class="new-note">
    <label>Title</label>
    <input v-model="note.title" type="text">

    <label>Priority</label>
    <div class="priority">
      <label for="one"><input type="radio" name="priority" id="one" value="low" v-model="note.priority"> <span>Low</span></label>
      <label for="two"><input type="radio" name="priority" id="two" value="middle" v-model="note.priority"> <span>Middle</span></label>
      <label for="three"><input type="radio" name="priority" id="three" value="high" v-model="note.priority"> <span>High</span></label>
    </div>
    <label>Description</label>
    <textarea v-model="note.descr"></textarea>
    <button class="btn btnPrimary" @click="addNote">New note</button>
  </div>
</template>

<script>
export default {
  props: {
    note: {
      type: Object,
      required: true
    }
  },
  methods: {
    addNote () {
      this.$emit('addNote', this.note)
    }
  }
}
</script>

<style lang="scss">
.new-note {
  text-align: center;
}
.priority {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
  label {
    width: 33%;
    flex-shrink: 0;
    flex-grow: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    input {
      flex-shrink: 0;
      flex-grow: 0;
      margin: 0 5px 0 0;
      width: 12px;
      height: 12px;
    }
  }
}
</style>

