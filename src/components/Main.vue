<template>
    <v-content>
        <v-container class="container">
            <v-row>
                <v-col class="col line-separator">
                    <div class="scrollable pr-3">
                        <OptionsPanel @inputRows="getInputRows" @posterOptions="emitPosterOptions"/>
                    </div>
                </v-col>
                <v-col class="col">
                    <div class="scrollable pr-3 display-panel">
                        <DisplayPanel :inputRows="inputRows" :posterOptions="posterOptions" /> 
                    </div>
                </v-col>
            </v-row>
        </v-container>
    </v-content>
</template>

<script>
import OptionsPanel from '../components/OptionsPanel.vue'
import DisplayPanel from '../components/DisplayPanel.vue'

export default {
    components: {
        OptionsPanel,
        DisplayPanel
    },
    data: function() {
        return {
            inputRows: Object,
            posterOptions: Object
        }
    },
    methods: {
        getInputRows: function(inputRows) {
            this.inputRows = inputRows;
        },
        setValue: function(inputValue) {
            this.input = inputValue;
        },
        emitPosterOptions(posterOptions) {
            this.posterOptions = posterOptions;
        }
    }
}
</script>

<style scoped>
    .container {
        min-height: 86vh;
        display: flex;
        justify-content: center;
    }
    .col {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .scrollable {
        max-height: 90vh;
        flex-grow: 1;
        overflow-y: auto;
        overflow-x: hidden;
        display: flex;
        justify-content: center;
    }
    .line-separator {
        border-right: 1px solid #c2c2c2;
    }
    .display-panel {
        direction: rtl;
    }
</style>