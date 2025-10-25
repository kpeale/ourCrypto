<template>
  <header class="w-full mx-auto fixed z-50 top-0">
    <nav
      className="flex flex-row items-center justify-between container  mx-auto  transition-all duration-300"
    >
      <div>
        <img src="/public/logo.png" alt="logo" class="lg:w-[155] lg:h-[38px]" />
      </div>

      <div class="flex flex-row gap-6">
        <router-link to="/"></router-link>
      </div>
    </nav>
  </header>
</template>

<script lang="ts">
export default {
  name: 'NavBar',
}
</script>
