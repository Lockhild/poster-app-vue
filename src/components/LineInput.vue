<template>
    <div>
        <input type="text" placeholder="Enter a line..." v-model="text" 
               @keyup="$emit('textEntered', text, id)">
        <span @click="$emit('rowID', id)">X</span>
    </div>
</template>

<script>
export default {
    props: {
        inputID: Number
    },
    name: 'LineInput',
    data: function() {
        return {
            text: '',
            id: null
        }
    },
    methods: {
    },
    mounted: function() {
        this.id = this.inputID;
    }
}
</script>

<style>

</style>