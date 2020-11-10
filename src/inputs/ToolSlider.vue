<style>
    .tool-input input {
        -moz-appearance: textfield;
    }
    .tool-input input::-webkit-outer-spin-button,
    .tool-input input::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }
</style>

<template>
    <v-row>
        <v-col class="py-1">
            <v-slider
                v-model="value"
                :label="label"
                :min="min"
                :max="max"
                @change="sendCmd"
                :prepend-icon="prependIcon"
                hide-details>

                <template v-slot:append>
                    <v-text-field
                        v-model="value"
                        class="mt-0 pt-0 tool-input"
                        hide-details
                        single-line
                        type="number"
                        style="width: 80px"
                        @change="sendCmd"
                    ></v-text-field>
                </template>
            </v-slider>
        </v-col>
    </v-row>
</template>


<script>
    export default {
        data: function() {
            return {
                value: this.target * this.multi,
            }
        },
        props: {
            target: {
                type: Number,
                required: true,
            },
            command: {
                type: String,
                required: true,
            },
            attributeName: {
                type: String,
                required: false,
                default: ''
            },
            label: {
                type: String,
                required: false,
                default: ''
            },
            prependIcon: {
                type: String,
                required: false,
                default: ''
            },
            attributeScale: {
                type: Number,
                required: false,
                default: 1
            },
            min: {
                type: Number,
                required: false,
                default: 0
            },
            max: {
                type: Number,
                required: false,
                default: 100
            },
            extenderSteps: {
                type: Number,
                required: false,
                default: 100
            },
            extender: {
                type: Boolean,
                required: false,
                default: false
            },
            multi: {
                type: Number,
                required: false,
                default: 1
            },
        },
        computed: {

        },
        methods: {
            sendCmd() {
                this.$socket.sendObj('printer.gcode.script', { script: this.command+' '+this.attributeName+(this.value*this.attributeScale).toFixed(0) });
            },
        },
        watch: {
            target: function() {
                this.value = this.target * this.multi;
            },
        },
        created: function() {
        }
    }
</script>
