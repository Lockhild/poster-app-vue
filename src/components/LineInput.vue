<template>
    <v-text-field
        label="Poster row" 
        v-model="text" 
        clearable="clearable"
        counter="25"
        maxlength="25"
        @keyup="$emit('textEntered', text, id)">
        
        <v-icon class="icon" slot="append" dense @click="deleteRow">mdi-delete-outline</v-icon>
    </v-text-field>
</template>

<script>
export default {
    props: {
        inputID: Number,
        inputText: String
    },
    name: 'LineInput',
    data: function() {
        return {
            text: this.inputText,
            id: null,
            clearable: true
        }
    },
    methods: {
        deleteRow: function() {
            this.$emit('rowID', this.id);
        }
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
        color: #FD6F6F;
    }
</style>