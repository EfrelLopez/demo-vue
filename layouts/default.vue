<template>
    <v-app dark>
        
        <dr-navigation-drawer :clipped="clipped" :drawer="drawer" :items="items"/>

        <dr-nav-bar :clipped="clipped" :drawer="drawer" :title="title"/>

        <v-main>
            <v-container>
                <nuxt />
            </v-container>
        </v-main>

        <dr-footer :fixed="fixed"/>

    </v-app>
</template>

<script>

import NavigatorDrawer from '../components/NavigationDrawer'
import NavBar from '../components/NavBar'
import Footer from '../components/Footer'

export default {
    components: {
        'dr-navigation-drawer': NavigatorDrawer,
        'dr-nav-bar': NavBar,
        'dr-footer': Footer
    },
    data () {
        return {
            clipped: false,
            drawer: false,
            fixed: true,
            items: [
                {
                    icon: 'mdi-book',
                    title: 'Category',
                    to: '/'
                },
                {
                    icon: 'mdi-cart',
                    title: 'Shopping Cart',
                    to: '/cart'
                }
            ],
            title: 'Café Gitane'
        }
    }
}
</script>

<style>
</style>
