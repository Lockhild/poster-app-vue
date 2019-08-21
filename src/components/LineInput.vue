<template>
    <v-text-field 
        label="Poster row" 
        v-model="text" 
        clearable="true"
        counter="25"
        maxlength="25"
        @keyup="$emit('textEntered', text, id)">

        <v-icon class="icon" slot="append" dense @click="$emit('rowID', id)">mdi-delete-outline</v-icon>
    </v-text-field>
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

<style scoped>
    .icon {
        transition: all .3s;
    }
    .icon:hover {
        color: #d11a2a;
    }
</style>