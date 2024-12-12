<script>
export default {
  data() {
    return {
      name: "Kamrul Hasan",
      status: 'pending',
      tasks: ['one', 'two', 'three'],
      link: 'https://github.com/kamrulWSIT/vue_practice'
    }
  },
  methods: {
    toggleStatus() {
      if (this.status === 'active') {
        this.status = 'pending'
      }
      else if (this.status === 'pending') {
        this.status = 'inactive'
      }
      else {
        this.status = 'active'
      }
    }
  }
}
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
  <a v-bind:href="link">Click for project repo</a>
  <a :href="link">Click for project repo</a>
  <br>
  <br>

  <button v-on:click="toggleStatus">click me</button>
  <button @click="toggleStatus">click me</button>

</template>
