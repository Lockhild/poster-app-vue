<template>
    <div>
        <label>{{ label }}</label>
        <input type="range" :min="min" :max="max" :value="value">
    </div>
</template>

<script>
    export default {
        props: ['label', 'min', 'max', 'value']
    }
</script>

<style>

</style>