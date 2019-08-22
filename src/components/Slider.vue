<template>
    <div>
        <div class="d-flex justify-space-between align-center">
            <v-subheader class="pl-0 label">{{label}}</v-subheader>
            <span class="v-counter theme--light">{{ counter }}</span>
        </div>
        <v-slider
            class="mx-n2 mt-n2"
            :thumb-size="30"
            :min="min"
            :max="max"
            :value="value"
            v-bind="counter"
        ></v-slider>
    </div>
</template>

<script>
    export default {
        props: ['label', 'min', 'max', 'value'],
        data: function() {
            return {
                counter: this.value
            }
        }
    }
</script>

<style scoped>
    .label {
        height: 30px;
    }
</style>