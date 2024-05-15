<template>
  <div class="child">
    <h2>Child Component</h2>
    <button @click="emitData">Kirim Data</button>
    <slot name="childSlot" :data="data"></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: "Rosni Dwita - 223510686"
    };
  },
  methods: {
    emitData() {
      this.$emit('emitData', this.data);
    }
  }
}
</script>

<style scoped>
.child {
  font-family: Arial, sans-serif;
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 5px;
}

button {
  padding: 10px 20px;
  background-color: #273646;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #2f4052;
}
</style>
