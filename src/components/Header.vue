<template>
    <v-app-bar app class="header" id="header">
        <ColorPalleteModal class="mr-3" />
        <v-toolbar-title class="headline text-capitalize blue--text text--lighten-5 font-weight-bold">
            <span>Poster generator</span>
        </v-toolbar-title>
    </v-app-bar>
</template>

<script>
import ColorPalleteModal from '../components/ColorPalleteModal.vue'

export default {
    components: {
        ColorPalleteModal
    }
}
</script>

<style scoped>
    .header {
        background: #6B8798 !important;
    }
</style>