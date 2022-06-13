<template>
  <Head title="Users" />
  <div class="d-flex justify-content-between align-items-center mb-3">
    <h2 class="mb-3">Users Page</h2>
    <div class="d-flex">
      <input
        v-model="search"
        class="form-control me-2"
        type="search"
        placeholder="Search"
        aria-label="Search"
      />
      <button class="btn btn-outline-success" type="submit">Search</button>
    </div>
  </div>

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

<script setup>
import { ref } from "@vue/reactivity";
import { defineComponent, watch } from "@vue/runtime-core";
import Pagination from "../Shared/Pagination.vue";
import { Inertia } from "@inertiajs/inertia";

defineComponent({ Pagination });
let props = defineProps({ users: Object, filters: Object });

let search = ref(props.filters.search);

watch(search, (value) => {
  console.log("changed" + value);
  Inertia.get(
    "/users",
    { search: value },
    {
      preserveState: true,
      replace: true,
    }
  );
});
</script>

<style lang="scss" scoped>
</style>
