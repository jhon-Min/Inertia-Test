<template>
  <Nav />

  <section class="container my-5">
    <slot />
  </section>
</template>

<script>
import Nav from "./Nav.vue";

export default {
  components: { Nav },
};
</script>

