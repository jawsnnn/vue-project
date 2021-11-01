<template>
    <div>
      <nav class = "navbar navbar-expand-lg navbar-dark bg-dark shadow">
        <NuxtLink to="/" class="navbar-brand">Home</NuxtLink>
        <NuxtLink to="/about" class="nav-link">About</NuxtLink>
      </nav>
      <div class="col-md-8 offset-md-2 mt-3 mb-5 dark-banner shadow">
        <h1 class="lime-header">Notes</h1>
          <table class="table-dark col-md-8 offset-md-2 mb-3">
              <thead>
              <tr>
                <th scope="col" class="table-dark text-center">Id</th>
                <th scope="col" class="table-dark text-left pl-3">Note</th>
                <th scope="col" class="table-dark text-center">Completed</th>
              </tr>
              </thead>
                <tbody>
              <tr v-for="note in message" v-bind:key="note.id">
                  <td class="table-dark  text-center">{{ note.id }}</td>
                  <td class="table-dark  text-left pl-3">{{ note.text }}</td>
                  <td class="table-dark  text-center">{{ note.completed }}</td>
              </tr>
                </tbody>
          </table>
      </div>
    </div>
</template>

<script>
import io from 'socket.io-client';

var socket = io.listen('http://150.136.52.96:8000')
export default {
  data() {
    return {
      message: null
    }
  },
  mounted() {
    this.$axios.get('/api/notes')
    .then(response => {
      this.message = response.data
    })
  },
  getRealTimeData() {
    socket.on('create_note', (data) => {
      mounted()
    })
  }
}
</script>

<style>
.navbar-brand {
  font-size: 1.5rem;
  font-weight: bold;
}
.nav-link:hover {
  font-size: 1.2rem;
  font-weight: bold;
  color: pink;
  --tw-text-opacity: 1;
}
.nav-link {
  font-size: 1.2rem;
  font-weight: bold;
  color: rgba(0,220,130,var(--tw-text-opacity));
  --tw-text-opacity: 1;
}

.lime-header {
  color: lawngreen;
  font-size: 2rem;
  font-weight: bold;
}

.dark-banner {
  background-color: rgb(42, 48, 43);
  color: lightgreen;
  padding: 10px;
  text-align: center;
}
</style>
