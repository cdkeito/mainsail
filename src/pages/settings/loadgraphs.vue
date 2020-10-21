<style>
    .load-graph-img {
        max-width: 590px;
        max-height: 600px;
        margin-left: 50px;
        margin-bottom: 7px;
        filter: invert(100);
    }
</style>

<template>
    <div>
        <v-row>
            <v-col class="col-12 col-md-6 col-lg-4">
                <v-card class="mt-6">
                    <v-toolbar flat dense >
                        <v-toolbar-title>
                            Load MCU
                            <v-btn @click="regenLOADMCU" style="position: absolute;right: 7px;"><v-icon class="mr-1">mdi-refresh</v-icon></v-btn>
                        </v-toolbar-title>
                    </v-toolbar>

                    <v-card-text class="pb-0">
                        <img class="load-graph-img" src="https://user-images.githubusercontent.com/4675358/43595300-38f04b64-9674-11e8-9605-788781915139.png">
                    </v-card-text>
                </v-card>
            </v-col>
            <v-col class="col-12 col-md-6 col-lg-4">
                <v-card class="mt-6">
                    <v-toolbar flat dense >
                        <v-toolbar-title>
                            Load MCU Z
                            <v-btn @click="regenLOADMCU" style="position: absolute;right: 7px;"><v-icon class="mr-1">mdi-refresh</v-icon></v-btn>
                        </v-toolbar-title>
                    </v-toolbar>

                    <v-card-text class="pb-0">
                        <img class="load-graph-img" src="https://user-images.githubusercontent.com/4675358/43595300-38f04b64-9674-11e8-9605-788781915139.png">
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
        <v-row>
            <v-col class="col-12 col-md-6 col-lg-4">
                <v-card class="mt-6">
                    <v-toolbar flat dense >
                        <v-toolbar-title>
                            Load System MCU
                            <v-btn @click="regenLOADMCU" style="position: absolute;right: 7px;"><v-icon class="mr-1">mdi-refresh</v-icon></v-btn>
                        </v-toolbar-title>
                    </v-toolbar>

                    <v-card-text class="pb-0">
                        <img class="load-graph-img" src="https://user-images.githubusercontent.com/4675358/43595300-38f04b64-9674-11e8-9605-788781915139.png">
                    </v-card-text>
                </v-card>
            </v-col>
            <v-col class="col-12 col-md-6 col-lg-4">
                <v-card class="mt-6">
                    <v-toolbar flat dense >
                        <v-toolbar-title>
                            Load System Z
                            <v-btn @click="regenLOADMCU" style="position: absolute;right: 7px;"><v-icon class="mr-1">mdi-refresh</v-icon></v-btn>
                        </v-toolbar-title>
                    </v-toolbar>

                    <v-card-text class="pb-0">
                        <img class="load-graph-img" src="https://user-images.githubusercontent.com/4675358/43595300-38f04b64-9674-11e8-9605-788781915139.png">
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </div>
</template>

<script>
    /*
    import { mapState, mapActions } from 'vuex';

    export default {
        computed: {
        },
        methods: {
        }
    }
    */
</script>
