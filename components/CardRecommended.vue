<template>
    <div>
        <h2 class="font-weight-black ml-7 mb-2">Promociones</h2>
        <v-card
            shaped
            dark 
        >
            <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                    <v-card-title
                        class="text-subtitle-2"
                        v-text="name"
                    ></v-card-title>

                    <v-card-subtitle v-text="description"></v-card-subtitle>

                    <v-card-action>
                        <v-btn
                            elevation="3"
                            rounded
                            color="deep-purple lighten-2"
                            class="ml-3 mb-0"
                        >
                            Select
                        </v-btn>
                    </v-card-action>
                </div>

                <v-avatar
                    class="ma-3"
                    size="100"
                    elevation="6"
                >
                    <v-img 
                        :src="imagen"
                        style="border-radius: 50%"
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
                </v-avatar>

            </div>
        </v-card>
    </div>
</template>

<script>
    export default {
        props:[
            'name',
            'description',
            'imagen'
        ],
        data: () => ({
            loading: false,
        }),
        methods: {
            reserve () {
                this.loading = true
                setTimeout(() => (this.loading = false), 2000)
            },
        },
        created(){ 
            console.log(this.name);
            console.log(this.description);
            console.log(this.imagen);
        }
    }
</script>

<style>
    .font-pro{
        font-size: 25px;
    }
</style>