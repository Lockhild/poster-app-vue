<template>
    <div>
        <div class="text-area">
            <div v-for="(row, index) in inputRows" 
                 v-bind:key="index" 
                 class="area-row">
                 
                 <DisplayRow :textRow="row" />

            </div>
        </div>
    </div>
</template>

<script>
import DisplayRow from '../components/DisplayRow.vue'

export default {
    name: 'DisplayPanel',
    props: ['inputRows'],
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

<style>
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
    .area-row:nth-child(even):before {
        content: '';
        position: absolute;
        height: 1px;
        width: 90%;
        background: #dbdbdb;
        top: 0;
        left: 5%;
        z-index: -1;
    }
    .area-row:nth-child(even):after {
        content: '';
        position: absolute;
        height: 1px;
        width: 90%;
        background: #dbdbdb;
        top: 100%;
        left: 5%;
        z-index: -1;
    }
</style>