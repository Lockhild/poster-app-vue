<template>
  <span 
    class="span-text-row"
    v-bind:style="{fontSize: fontSize + 'px'}" >

    {{ textRow }}</span>
</template>

<script>
import { log } from 'util';
import { setTimeout } from 'timers';
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
    },
    watch: {
        textRow: function() {
            setTimeout(() => {
                enlargeTextOutside();
            }, 1);
        }
    }
}

function enlargeTextOutside() {

    var elements = Array.from(document.getElementsByClassName("span-text-row"));
    
    for(var i = 0; i < elements.length; i++) {
        var currentSize = 10 ;
        elements[i].style.fontSize = currentSize + 'px';
        var elementWidth = elements[i].getBoundingClientRect().width;
        var containerWidth = elements[i].parentElement.getBoundingClientRect().width - 2;
        while(elementWidth < containerWidth) {
            currentSize += 1;
            elements[i].style.fontSize = currentSize + 'px';
            elementWidth = elements[i].getBoundingClientRect().width;

            if(currentSize > 350) {
                break;
            }
        }
    }
}
</script>

<style scoped>
    .span-text-row {
        white-space: nowrap;
    }
</style>