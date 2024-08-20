<template>
  <div class="flex items-center justify-center min-h-screen">
    <div class="w-full max-w-md bg-white shadow-md rounded px-4 py-4 sm:px-8 sm:py-6">
      <h1 class="text-xl sm:text-2xl font-bold text-center mb-4 sm:mb-6">Login</h1>
      <ul v-if="errors" class="mb-4 text-red-500 text-sm">
        <li v-for="(v, k) in errors" :key="k">{{ k }} {{ v | error }}</li>
      </ul>
      <form @submit.prevent="onSubmit(email, password)">
        <div class="mb-4">
          <input class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
            type="email" v-model="email" placeholder="Email" />
        </div>
        <div class="mb-4">
          <input class="w-full px-3 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
            type="password" v-model="password" placeholder="Password" />
        </div>
        <button
          class="w-full bg-blue-500 text-white font-semibold py-2 rounded-lg hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">
          Login
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      email: null,
      password: null
    };
  },
  methods: {
    onSubmit(email, password) {
      this.$store
        .dispatch("login", { email, password })
        .then(() => this.$router.push({ name: "home" }));
    }
  },
};
</script>
