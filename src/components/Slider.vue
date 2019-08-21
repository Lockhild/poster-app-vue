<template>
    <div>
        <v-subheader class="pl-0 label">{{label}}</v-subheader>
        <v-slider
            class="mx-n2"
            thumb-label
            :thumb-size="30"
            :min="min"
            :max="max"
            :value="value"
        ></v-slider>
    </div>
</template>

<script>
    export default {
        props: ['label', 'min', 'max', 'value'],
    }
</script>

<style scoped>
    .label {
        height: 30px;
    }
</style>