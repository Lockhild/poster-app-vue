<template>
    <div>
        <div 
            class="text-area"
            :style="{ padding: posterOptions.padding + 'px' }">
            <div v-for="(row, index) in inputRows" 
                 v-bind:key="index" 
                 class="area-row"
                 :style="{
                     background: posterOptions.background + ' !important',
                     lineHeight: posterOptions.lineHeight
                  }">
                 
                 <DisplayRow :textRow="row" />

            </div>
        </div>
    </div>
</template>

<script>
import DisplayRow from '../components/DisplayRow.vue'

export default {
    name: 'DisplayPanel',
    props: ['inputRows', 'posterOptions'],
    components: {
        DisplayRow
    },
    data: function() {
        return {

        }
    },
    methods: {
    }
}
</script>

<style scoped>
    .text-area {
        width: 380px;
        height: 100%;
        min-height: 500px;
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
</style>