<template>
  <section>
    <div v-if="$route.query.message" class="alert alert-danger mb-3">
      Need login first
    </div>
    <form @submit.prevent="onSubmit">
      <div class="form-group">
        <input type="text" class="form-control" />
      </div>
      <p>
        <nuxt-link exact active-class="active" class="nav-link" to="/"
          >To home page</nuxt-link
        >
      </p>
      <button class="btn btn-primary" type="submit">Login</button>
    </form>
  </section>
</template>

<style scoped>
form {
  width: 500px;
  margin: 0 auto;
}
</style>
<script>
export default {
  layout: "empty",
  methods: {
    onSubmit() {
      this.$store.dispatch("login");
      this.$router.push("/");
    }
  }
};
</script>
