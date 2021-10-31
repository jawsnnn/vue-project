<template>
    <div>
      <nav class = "navbar navbar-expand-lg navbar-dark bg-dark shadow">
        <NuxtLink to="/" class="navbar-brand">Home</NuxtLink>
        <NuxtLink to="/about" class="nav-link">About</NuxtLink>
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
      message: "this is a message"
    }
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
</style>
