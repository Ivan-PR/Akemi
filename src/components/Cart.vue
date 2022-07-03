<template>
    <a class="nav-item nav-link text-white ps-3 pe-3 py-0 my-0" href="#">{{quantity}} Items</a>
    <a class="nav-item nav-link text-white ps-3 pe-3 py-0 my-0" href="#">0€</a>
</template>

<script>

export default {
    props: {
        quantity: {
            type: String,
            default: 'Null',
        },
    },
}
</script>

<style>

</style>