<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container">
      <a class="navbar-brand" href="#"
        >My App
        <span class="small text-black-50">Welcome, {{ username }} </span></a
      >
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav ms-auto">
          <NavLink href="/" :active="$page.component === 'Welcome'"
            >Home</NavLink
          >
          <NavLink href="/users" :active="$page.component === 'Users'"
            >User</NavLink
          >
          <NavLink href="/settings" :active="$page.component === 'Settings'"
            >Setting</NavLink
          >
          <Link
            href="/logout"
            method="post"
            class="btn btn-danger btn-sm ms-2"
            as="button"
            >Logout</Link
          >
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import NavLink from "./NavLink.vue";

export default {
  components: { NavLink },

  computed: {
    username() {
      return this.$page.props.auth.user.username;
    },
  },
};
</script>

<style lang="scss" scoped>
</style>
