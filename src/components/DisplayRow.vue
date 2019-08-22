<template>
  <span 
    ref="textRow" 
    v-bind:style="{fontSize: fontSize + 'px'}" 
    @change="changed">

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
            fontSize: 60
        }
    },
    methods: {
        changed: function() {
            console.log("changed");
        }
    },
    watch: {
        // textRow: function() {
        //     var textRow = this.$refs.textRow;
        //     var parentRow = textRow.parentElement;

        //     // var textRowWidth = textRow.getBoundingClientRect().width;
        //     // var textRowHeight = textRow.getBoundingClientRect().height;
        //     // var parentRowWidth = parentRow.getBoundingClientRect().width;
        //     // var parentRowHeight = parentRow.getBoundingClientRect().height;

        //     // console.log(parentRow.offsetWidth);

        //     this.fontSize += 10;

        //     for(var i = 0; i < 100; i++) {
        //         console.log("textRow.offsetWidth: " + textRow.offsetWidth);
        //         console.log("parentRow.offsetWidth: " + parentRow.offsetWidth);
        //         if(textRow.offsetWidth < parentRow.offsetWidth) {
        //             this.fontSize++;
        //             console.log("fontSize: " + this.fontSize);
        //         } else {
        //             break;
        //         }
        //     }
        // }
    }
}
</script>

<style>

</style>