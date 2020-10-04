<template>
    <v-footer
        :absolute="!fixed"
        dark
        app
    >
        <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
</template>

<script>
export default {
    props:[
        'fixed'
    ]
}
</script>

<style>

</style>