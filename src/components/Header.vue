<template>
  <nav class="bg-white border-b border-gray-200 fixed top-0 left-0 right-0 z-50">
    <div class="container mx-auto flex justify-between items-center py-4">
      <router-link class="text-xl font-bold text-gray-900" :to="{ name: 'home' }">
        James Airline
      </router-link>
      <ul class="flex space-x-6">
        <li>
  <router-link :to="{ name: 'login' }" class="text-gray-700 hover:text-gray-900">
    <i class="ion-compose"></i> Login/Register
  </router-link>

  </li>
      </ul>
    </div>
  </nav>
</template>

<script>

export default {
  name: "Header",
};
</script>
