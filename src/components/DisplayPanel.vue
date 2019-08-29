<template>
    <div>
        <v-menu
            v-model="menu"
            :close-on-content-click="false"
            nudge-width="300"
            offset-y
            :absolute="absolute"
            nudge-bottom="30"
            nudge-left="200">
        <template v-slot:activator="{ on }">
            <div 
                class="text-area"
                :style="{ 
                    padding: posterOptions.padding + 'px',
                    background: posterOptions.background
                }"
                v-on="on">
                <div v-for="(row, index) in inputRows" 
                    v-bind:key="index" 
                    class="area-row"
                    :style="{
                        lineHeight: posterOptions.lineHeight + 'px',
                        background: posterRowOptions.textBackground
                    }"
                    :class="{ 'text-uppercase': posterOptions.uppercase }">
                    
                    <DisplayRow :textRow="row" :posterRowOptions="posterRowOptions" />

                </div>
            </div>
        </template>

        <v-card>
            <div class="options-modal">
                <OptionsModal @posterRowOptions="setPosterRowOptions" />
            </div>
        </v-card>
        </v-menu>
    </div>
</template>

<script>
import DisplayRow from '../components/DisplayRow.vue'
import OptionsModal from '../components/OptionsModal.vue'

export default {
    name: 'DisplayPanel',
    props: ['inputRows', 'posterOptions'],
    components: {
        DisplayRow,
        OptionsModal
    },
    data: function() {
        return {
            menu: false,
            absolute: true,
            left: true,
            posterRowOptions: Object
        }
    },
    methods: {
        setPosterRowOptions(posterRowOptions) {
            this.posterRowOptions = posterRowOptions;
        }
    }
}
</script>

<style scoped>
    .text-area {
        min-width: 380px;
        height: 100%;
        border: 1px solid #dcdcdc;
        display: flex;
        flex-direction: column;
    }
    .area-row {
        flex-grow: 1;
        width: 100%;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 50px;
    }
    /* .area-row:nth-child(even):before {
        content: '';
        position: absolute;
        height: 1px;
        width: 90%;
        background: #dbdbdb;
        top: 0;
        left: 5%;
    }
    .area-row:nth-child(even):after {
        content: '';
        position: absolute;
        height: 1px;
        width: 90%;
        background: #dbdbdb;
        top: 100%;
        left: 5%;
    } */
    .area-row:nth-child(even) {
        background: #f5f5f5;
    }
    .options-modal {
        padding: 20px 27px;
    }
</style>