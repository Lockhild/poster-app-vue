<template>
  <span 
    ref="textRowRef" 
    v-bind:style="{fontSize: fontSize + 'px'}" >

    {{ textRow }}</span>
</template>

<script>
export default {
    name: 'DisplayRow',
    props: {
        textRow: String
    },
    data: function() {
        return {
            fontSize: 30
        }
    },
    methods: {
        changed: function() {
            console.log("changed");
        },
        enlargeText: function() {
            // var textRow = this.$refs.textRowRef;
            // var parentRow = textRow.parentElement;

            // for(var i = 0; i < 10; i++) {
            //     this.fontSize += 10;
            //     console.log(`Text Row in loop: ${textRow.clientWidth}`);
            //     textRow = this.$refs.textRowRef;
            // }

            // console.log(`Text Row: ${textRow.clientWidth}`);
            // console.log(`Parent Row: ${parentRow.clientWidth}`);
        }
    },
    watch: {
        textRow: function() {
            // var textRow = this.$refs.textRow;
            // var parentRow = textRow.parentElement;

            // // var textRowWidth = textRow.getBoundingClientRect().width;
            // // var textRowHeight = textRow.getBoundingClientRect().height;
            // // var parentRowWidth = parentRow.getBoundingClientRect().width;
            // // var parentRowHeight = parentRow.getBoundingClientRect().height;

            // // console.log(parentRow.offsetWidth);

            // this.fontSize += 10;

            // for(var i = 0; i < 100; i++) {
            //     console.log("textRow.offsetWidth: " + textRow.offsetWidth);
            //     console.log("parentRow.offsetWidth: " + parentRow.offsetWidth);
            //     if(textRow.offsetWidth < parentRow.offsetWidth) {
            //         this.fontSize++;
            //         console.log("fontSize: " + this.fontSize);
            //     } else {
            //         break;
            //     }
            // }
            this.enlargeText();
        }
    }
}
</script>

<style>

</style>