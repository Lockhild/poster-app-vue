<template>
    <v-content class="main">
        <OptionsPanel v-on:inputRows="getInputRows"/>
        <DisplayPanel :inputRows="inputRows"/>
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
    .main {
        display: flex;
        justify-content: space-around;
        margin: 100px 0;
    }
    .main:after {
        content: "";
        height: 100%;
        width: 1px;
        background: grey;
        position: absolute;
        top: -10%;
    }
</style>