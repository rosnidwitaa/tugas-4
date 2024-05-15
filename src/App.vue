<template>
  <div class="parent">
    <h1>Parent Component</h1>
    <child-component @emitData="handleData">
      <template v-slot:childSlot="{ data }">
        <div class="child-slot">
          {{ data }}
        </div>
      </template>
    </child-component>
    <div class="received-data" v-if="receivedData">
      <p>Data yang diterima: {{ receivedData }}</p>
    </div>
  </div>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      receivedData: null
    }
  },
  methods: {
    handleData(data) {
      this.receivedData = data;
    }
  }
}
</script>

<style scoped>
.parent {
  font-family: Arial, sans-serif;
  padding: 20px;
}

.received-data {
  margin-top: 20px;
  background-color: #408db9;
  padding: 10px;
  border-radius: 5px;
}

.child-slot {
  background-color: #32566b;
  padding: 10px;
  border-radius: 5px;
}
</style>
