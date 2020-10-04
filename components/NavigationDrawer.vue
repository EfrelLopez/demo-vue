<template>
    <v-navigation-drawer
        :drawer=drawer
        :clipped=clipped
        dark
        fixed
        app
    >
        <v-list-item>
            <v-list-item-content>
                <v-list-item-title class="title">
                    Menu
                </v-list-item-title>
                <v-list-item-subtitle>
                   Select a menu option
                </v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>
    
        <v-list>
            <v-list-item
                v-for="(item, i) in items"
                :key="i"
                :to="item.to"
                router
                exact
            >
                <v-list-item-action>
                    <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                    <v-list-item-title v-text="item.title" />
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script>
export default {
    props:[
        'clipped',
        'drawer',
        'items'
    ],
    data() {
      return {

      }
    }
}
</script>

<style>
</style>