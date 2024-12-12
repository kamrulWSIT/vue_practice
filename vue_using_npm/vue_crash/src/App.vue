<script setup>
import { ref } from 'vue';

const name = ref('Kamrul Hasan');
const status = ref('active');
const tasks = ref(['one', 'two', 'three']);
const toggleStatus = () => {
  if (status.value === 'active') {
    status.value = 'pending'
  }
  else if (status.value === 'pending') {
    status.value = 'inactive'
  }
  else {
    status.value = 'active'
  }
};

</script>

<template>

  <h1>
    {{ name }}
  </h1>
  <p v-if="status === 'active'">user is active</p>
  <p v-else-if="status === 'pending'">user is pending</p>
  <p v-else>user is inactive</p>


  <h3>Tasks</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>


  <button @click="toggleStatus">change status</button>


</template>
