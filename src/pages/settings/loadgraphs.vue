<style>
    .load-graph-img {
        filter: invert(100);
    }
</style>

<template>
    <div>
        <v-card class="mt-6">
            <v-toolbar flat dense >
                <v-toolbar-title>
                    Load Graphs
                    <v-btn @click="regenLoadGraphs" style="position: absolute;right: 7px;"><v-icon class="mr-1">mdi-refresh</v-icon> Generate</v-btn>
                </v-toolbar-title>
            </v-toolbar>

            <v-card-text class="pb-0">
                <v-row>
                    <v-col v-for="(item, key) in imageURLS" :key="key" cols="3" class="col-12 col-md-6 col-lg-4">
                        <div class="subheading">
                            {{ key }}
                        </div>
                        <v-img class="load-graph-img" max-width="590" max-height="600" :src="imgURL(key)"></v-img>
                    </v-col>
                </v-row>
            </v-card-text>
        </v-card>
    </div>
</template>

<script>
    import { mapState } from 'vuex';
    import axios from 'axios';

    export default {
        data: () => ({
            imgCacheKey: +new Date(),
            imgHost: 'http://192.168.178.37',
            imageURLS: {},
        }),
        computed: {
            ...mapState({
                hostname: state => state.socket.hostname,
                port: state => state.socket.port,
                loadings: state => state.loadings,
            }),
        },
        methods: {
            regenLoadGraphs() {
                this.$toast.info("Scheduling loadgraphs for regeneration. Please wait.");
                axios
                    .post('//' + this.hostname + ':' + this.port + '/loadgraohs/regen/all')
                    .then((result) => {
                        this.imgCacheKey = +new Date();
                        this.$toast.success("Loadgraphs successfully scheduled for regeneration.");
                        this.imageURLS = result.data.result;
                    })
                    .catch((error) => {
                        this.$toast.error("Error! " + error);
                    });
            },
            imgURL: function(key) {
                return this.imgHost + this.imageURLS[key] + '?rnd=' + this.imgCacheKey;
            },
        }

    }
</script>
