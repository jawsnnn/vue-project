<template>
  <div>
      <nav class = "navbar navbar-expand-lg navbar-dark bg-dark shadow">
        <NuxtLink to="/" class="nav-link">Home</NuxtLink>
        <NuxtLink to="/about" class="navbar-brand">About</NuxtLink>
      </nav>
      <div class="col-md-8 offset-md-2 mt-3 dark-banner shadow">
          {{ message }}
        </div>
      </div>
</template>

<script>
export default {
  data() {
    return {
      message: "This is a simple VueJS application"
    }
  }
}
</script>
