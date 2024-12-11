<template>
  <header
    class="flex justify-between items-center bg-[#032541] text-white h-[3.9rem] text-[0.92rem] px-16"
  >
    <div class="flex items-center space-x-6 gap-4">
      <img src="../assets/logo.svg" class="h-16 w-40" alt="Logo" />
      <ul class="flex space-x-6">
        <li class="cursor-pointer">Movies</li>
        <li class="cursor-pointer">TV Shows</li>
        <li class="cursor-pointer">People</li>
        <li class="cursor-pointer">More</li>
      </ul>
    </div>

    <ul class="flex items-center space-x-6">
      <li class="cursor-pointer">+</li>
      <li class="cursor-pointer">EN</li>
      <li class="cursor-pointer">Login</li>
      <li class="cursor-pointer">Join TMDB</li>
      <li class="cursor-pointer">Search</li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>
