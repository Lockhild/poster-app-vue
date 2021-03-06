<template>
    <div class="options-panel">
        <div class="d-flex justify-space-between align-center mt-12">
            <v-btn class="text-none" small rounded color="primary" min-width="130" @click="addInputRow">
                <v-icon class="mr-1" size="18">mdi-plus</v-icon>
                Add row
            </v-btn>
            <v-switch 
                class="uppercase-switch" 
                v-model="posterOptions.uppercase" 
                label="Auto-uppercase" 
                color="primary"></v-switch>
        </div>
        <div class="text-inputs mt-6">
            <transition-group 
                name="list" 
                tag="div" 
                enter-active-class="animated zoomIn faster"
                leave-active-class="animated zoomOut faster">

                <LineInput v-for="(item, index) in inputRows" 
                            v-bind:key="index" 
                            v-on:textEntered="updateText"
                            v-on:rowID="deleteRow"
                            :inputID="index"
                            :inputText="item"
                            class="mt-n2" />
            </transition-group>
        </div>

        <v-divider class="mt-6 mb-5"></v-divider>

        <ColorInput @colorValue="setColor" @imageValue="setPosterImageBackground" label="Poster background" />
        <v-divider class="mt-10 mb-6"></v-divider>
        <Slider 
            label="Line height" 
            min="0" 
            max="400" 
            value="120"
            @sliderValue="setLineHeight" />
        <Slider 
            class="mt-n4" 
            label="Padding" 
            min="0" 
            max="100" 
            value="10"
            @sliderValue="setPadding" />

        <v-divider class="mt-1 mb-4"></v-divider>

        <ColorInput @colorValue="setBorderColor" @imageValue="setPosterBorderBackground" label="Poster border" />
        <Slider 
            class="mt-4" 
            label="Border width" 
            min="0" 
            max="100" 
            value="10"
            @sliderValue="setBorderWidth" />
        <Slider 
            class="mt-n4" 
            label="Border radius" 
            min="0" 
            max="100" 
            value="10"
            @sliderValue="setBorderRadius" />

        <v-divider class="mt-4 mb-6"></v-divider>

        <div>
            <v-subheader class="pl-0 label">Choose poster width</v-subheader>
            <div class="d-flex align-center">
                <input type="number" class="text-input">
                <v-icon class="icon" size="30">mdi-close</v-icon>
                <input type="number" class="text-input" disabled>
            </div>
        </div>

        <v-divider class="mt-9 mb-8"></v-divider>

        <v-btn
            outlined 
            rounded 
            color="primary"
            width="100%">Generate HTML / CSS code</v-btn>
        <v-btn
            rounded 
            color="primary"
            width="100%"
            class="mt-3">Download poster</v-btn>
    </div>
</template>

<script>
import LineInput from '../components/LineInput.vue'
import Slider from '../components/Slider.vue'
import ColorInput from '../components/ColorInput.vue'

export default {
    components: {
        LineInput,
        Slider,
        ColorInput
    },
    data: function() {
        return {
            inputRows: ['the sun is up', 'the sky is blue', 'it\'s beautiful', 'and so are you'],
            posterOptions: {
                background: '#fff',
                posterImageBackground: null,
                lineHeight: 0,
                padding: 0,
                uppercase: false,
                borderColor: '#666',
                posterBorderBackground: null,
                borderWidth: 20,
                borderRadius: 20
            }
        }
    },
    methods: {
        updateText: function(text, id) {
            this.inputRows.splice(id, 1, text);
            this.$emit('inputRows', this.inputRows);
        },
        addInputRow: function() {
            this.inputRows.push('');
            this.$emit('inputRows', this.inputRows);
        },
        deleteRow: function(id) {
            this.$delete(this.inputRows, id);
            this.$emit('inputRows', this.inputRows);
        },
        setColor(colorValue) {
            this.posterOptions.background = colorValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setLineHeight(sliderValue) {
            this.posterOptions.lineHeight = sliderValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setPadding(sliderValue) {
            this.posterOptions.padding = sliderValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setPosterImageBackground(imageValue) {
            this.posterOptions.posterImageBackground = imageValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setBorderColor(colorValue) {
            this.posterOptions.borderColor = colorValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setPosterBorderBackground(imageValue) {
            this.posterOptions.posterBorderBackground = imageValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setBorderWidth(sliderValue) {
            this.posterOptions.borderWidth = sliderValue;
            this.$emit('posterOptions', this.posterOptions);
        },
        setBorderRadius(sliderValue) {
            this.posterOptions.borderRadius = sliderValue;
            this.$emit('posterOptions', this.posterOptions);
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
    .text-input {
        border: 1px solid #c2c2c2;
        height: 36px;
        border-radius: 5px;
        color: rgba(0, 0, 0, 0.87);
        padding: 0 8px;
        max-width: 165px;
    }
    .uppercase-switch {
        height: 28px;
        margin-top: 4px;
        padding: 0;
    }
/* 
    .list-item {
    display: inline-block;
    margin-right: 10px;
    }
    .list-enter-active, .list-leave-active {
    transition: all 1s;
    }
    .list-enter, .list-leave-to{
    opacity: 0;
    transform: translateY(30px);
    } */
</style>