<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <nuxt-link active-class="active" class="navbar-brand" to="#"
      >Nuxt SSR</nuxt-link
    >

    <div class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item ">
          <nuxt-link exact active-class="active" class="nav-link" to="/"
            >Home</nuxt-link
          >
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/about"
            >About</nuxt-link
          >
        </li>
        <li class="nav-item">
          <nuxt-link active-class="active" class="nav-link" to="/users"
            >Users</nuxt-link
          >
        </li>
        <li class="nav-item" v-if="!hasToken">
          <nuxt-link active-class="active" class="nav-link" to="/login"
            >Login</nuxt-link
          >
        </li>
        <li class="nav-item" v-else>
          <a
            href="#"
            @click.prevent="logout"
            active-class="active"
            class="nav-link"
            to="/login"
            >Logout</a
          >
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  computed: {
    hasToken() {
      return this.$store.getters.hasToken;
    }
  },
  methods: {
    logout() {
      this.$store.dispatch("logout");
      this.$router.push("login");
    }
  }
};
</script>
