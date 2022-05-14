<template>
  <Head title="Users" />
  <h2 class="mb-3">Users Page</h2>
  <table class="table table-striped table-hover mb-5">
    <thead>
      <tr>
        <th>#</th>
        <th>User</th>
        <th>Control</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="user in users.data" :key="user.id">
        <td>
          {{ user.id }}
        </td>
        <td>
          {{ user.name }}
        </td>
        <td>
          <Link :href="`/user/${user.id}/edit`" class="btn btn-primary btn-sm"
            >Edit</Link
          >
        </td>
      </tr>
    </tbody>
  </table>

  <!-- Paginator -->
  <Pagination :links="users.links" />
</template>

<script>
import Pagination from "../Shared/Pagination.vue";

export default {
  components: { Pagination },
  props: {
    users: Object,
  },
};
</script>

<style lang="scss" scoped>
</style>
