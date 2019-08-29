<template>
    <div>
        <v-select
            :items="fonts"
            label="Font family"
            outlined
            @change="setFontFamily">
        </v-select>

        <Slider 
            label="Font size" 
            min="0" 
            max="100" 
            :value="posterRowOptions.fontSize"
            @sliderValue="setFontSize" />

        <Slider 
            label="Font weight" 
            min="1" 
            max="9" 
            :value="posterRowOptions.fontWeight"
            @sliderValue="setFontWeight" />

        <Slider 
            label="Text position" 
            min="0" 
            max="100" 
            :value="posterRowOptions.textPosition"
            @sliderValue="setTextPosition" />        
        
        <Slider 
            label="Letter spacing" 
            min="0" 
            max="100" 
            :value="posterRowOptions.letterSpacing"
            @sliderValue="setLetterSpacing" />

        <ColorInput @colorValue="setTextColor" label="Text color" />

        <ColorInput @colorValue="setTextBackground" label="Text background" />
    </div>
</template>

<script>
import Slider from '../components/Slider.vue'
import ColorInput from '../components/ColorInput.vue'

export default {
    components: {
        Slider,
        ColorInput
    },
    data: () => ({
        fonts: ['Sans Serif', 'Times New Roman', 'Arial', 'Monospace'],
        posterRowOptions: {
            fontFamily: 'Times New Roman',
            fontSize: 50,
            fontWeight: 7,
            textPosition: 0,
            letterSpacing: 0,
            textColor: '#E9E98D',
            textBackground: '#757575'
        }
    }),
    methods: {
        setFontFamily(fontFamily) {
            this.posterRowOptions.fontFamily = fontFamily;
            this.$emit('posterRowOptions', this.posterRowOptions);
        },
        setFontSize(fontSize) {
            this.posterRowOptions.fontSize = fontSize;
            this.$emit('posterRowOptions', this.posterRowOptions);
        },
        setFontWeight(fontWeight) {
            this.posterRowOptions.fontWeight = fontWeight;
            this.$emit('posterRowOptions', this.posterRowOptions);
        },
        setTextPosition(textPosition) {
            this.posterRowOptions.textPosition = textPosition;
            this.$emit('posterRowOptions', this.posterRowOptions);
        },
        setLetterSpacing(letterSpacing) {
            this.posterRowOptions.letterSpacing = letterSpacing;
            this.$emit('posterRowOptions', this.posterRowOptions);
        },
        setTextColor(textColor) {
            this.posterRowOptions.textColor = textColor;
            this.$emit('posterRowOptions', this.posterRowOptions);
        },
        setTextBackground(textBackground) {
            this.posterRowOptions.textBackground = textBackground;
            this.$emit('posterRowOptions', this.posterRowOptions);
        }
    }
}
</script>

<style>

</style>