<template>
  <nav aria-label="Page navigation example">
    <ul class="pagination">
      <li
        class="page-item di"
        :class="{ disabled: !link.url, active: link.active }"
        v-for="link in links"
      >
        <Link class="page-link" :href="link.url" v-html="link.label" />
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: ["links"],
};
</script>

<style lang="scss" scoped>
</style>
