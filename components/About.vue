<template>
  <div>
      <nav class = "navbar navbar-expand-lg navbar-dark bg-dark shadow">
        <NuxtLink to="/" class="nav-link">Home</NuxtLink>
        <NuxtLink to="/about" class="navbar-brand">About</NuxtLink>
      </nav>
      <div class="mt-8 bg-white overflow-hidden sm:rounded-lg p-6">
        <p class = "mt-3 text-gray-600">
          {{ message }}
        </p>
      </div>
      </div>
</template>

<script>
export default {
  data() {
    return {
      message: "About this"
    }
  }
}
</script>
