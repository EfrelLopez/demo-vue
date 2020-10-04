<template>
    <div>
        <v-row justify="center mb-3">
            <h2 class="font-weight-black">
                Selecciona Producto
            </h2>
        </v-row>
        <v-carousel>
            <v-carousel-item 
                v-for="item of items" 
                :key="item.id"
            >
                <v-card
                    :loading="loading"
                    elevation="7"
                    shaped
                >
                    <v-img
                        height="250"
                        :src="item.imagen"
                    >
                        <template v-slot:placeholder>
                            <v-row
                                class="fill-height ma-0"
                                align="center"
                                justify="center"
                            >
                                <v-progress-circular
                                    indeterminate
                                    color="grey lighten-5"
                                ></v-progress-circular>
                            </v-row>
                        </template>
                    </v-img>

                    <v-card-title class="justify-center">{{item.nombre}}</v-card-title>

                    <v-card-text v-if="item.descripcion">
                        <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Provident, debitis?</div>
                    </v-card-text>

                    <v-card-actions>
                        <v-row
                            align="center"
                            justify="space-around"
                        >
                            <v-btn
                                elevation="3"
                                rounded
                                color="deep-purple lighten-2"
                                style="pr-2 pl-2"
                                @click="reserve"
                            >
                                Select
                            </v-btn>
                        </v-row>
                    </v-card-actions>
                </v-card>

            </v-carousel-item>
        </v-carousel>
    </div>
</template>

<script>
    export default {
        props:[
            'items'
        ],
        data: () => ({
            loading: false,
            selection: 1,
            attrs: {
                class: 'mb-6',
                boilerplate: true,
                elevation: 2,
            },
        }),
        methods: {
            reserve () {
                this.loading = true
                setTimeout(() => (this.loading = false), 2000)
            },
        },
    }
</script>

<style>

</style>