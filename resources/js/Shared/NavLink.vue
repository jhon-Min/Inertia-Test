<template>
    <Link class="nav-link" :class="{ 'active': active }"><slot /></Link>
</template>

<script>

export default {
    props: {
        active: Boolean
    }
}
</script>

<style lang="scss" scoped>
</style>
