<template>
    <v-content>
        <v-container class="container">
            <v-row>
                <v-col class="col">
                    <OptionsPanel v-on:inputRows="getInputRows"/>
                </v-col>
                <v-col class="col">
                    <DisplayPanel :inputRows="inputRows"/> 
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
            inputRows: Object
        }
    },
    methods: {
        getInputRows: function(inputRows) {
            this.inputRows = inputRows;
        },
        setValue: function(inputValue) {
            this.input = inputValue;
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
</style>