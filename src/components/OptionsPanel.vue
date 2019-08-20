<template>
    <div class="options-panel">
        <div class="d-flex justify-space-between align-center">
            <v-btn class="text-none" small rounded color="primary" min-width="130" @click="addInputRow">
                <v-icon class="mr-1" size="18">mdi-plus</v-icon>
                Add row
            </v-btn>
            <v-switch v-model="uppercase" label="Auto-uppercase" color="primary"></v-switch>
        </div>
        <div class="text-inputs">
            <LineInput v-for="(item, index) in inputRows" 
                       v-bind:key="index" 
                       v-on:textEntered="updateText"
                       v-on:rowID="deleteRow"
                       :inputID="index" />
        </div>
        <div>
            <!-- <ColorInput />
            <ImageUpload /> -->
        </div>
        <Slider label="Line height" min="0" max="100" value="45"/>
        <Slider label="Padding" min="0" max="100" value="65"/>
        <div>
            <label>Choose poster width</label>
            <input type="text" placeholder="Width...">
            <span>X</span>
            <input type="text" disabled>
        </div>
        <div>
            <button disabled>Download poster</button>
            <button>Generate poster</button>
        </div>
        <button>Generate HTML / CSS code</button>
    </div>
</template>

<script>
import LineInput from '../components/LineInput.vue'
import Slider from '../components/Slider.vue'
import ImageUpload from '../components/ImageUpload.vue'
import ColorInput from '../components/ColorInput.vue'

export default {
    components: {
        LineInput,
        Slider,
        ImageUpload,
        ColorInput
    },
    data: function() {
        return {
            inputRows: ['this', 'is', 'awesome'],
            uppercase: false
        }
    },
    methods: {
        updateText: function(text, id) {
            this.inputRows.splice(id, 1, text);
            this.$emit('inputRows', this.inputRows);
        },
        addInputRow: function() {
            this.inputRows.push('row');
            this.$emit('inputRows', this.inputRows);
        },
        deleteRow: function(id) {
            this.$delete(this.inputRows, id);
            this.$emit('inputRows', this.inputRows);
        }
    },
    mounted: function() {
        this.$emit('inputRows', this.inputRows);
    }
}
</script>

<style scoped>
    .options-panel {
        max-width: 360px;
    }
</style>