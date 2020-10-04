<template>
    <v-app-bar
        :clipped-left="clipped"
        fixed
        dense
        dark
        app
    >
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />

        <v-spacer />

        <v-toolbar-title v-text="title" />

        <v-spacer />

        <v-btn icon>
            <router-link to="/cart">
                <v-icon color="while">mdi-cart</v-icon>
            </router-link>
        </v-btn>


    </v-app-bar>
</template>

<script>
export default {
    props: [
        'clipped',
        'drawer',
        'title'
    ],
}
</script>