<template>
    <div>
        <button @click="isOpen=!isOpen">
            <v-icon class="blue--text text--lighten-5" size="30">mdi-chevron-down</v-icon>
        </button>
        <div class="modal" v-show="isOpen">
            <div class="modal-row">
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
            </div>
            <div class="modal-row">
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
            </div>
            <div class="modal-row">
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
                <span class="color">Lorem, ipsum.</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            isOpen: false
        }
    },
    methods: {
    }
}
</script>

<style scoped>
    .modal {
        position: absolute;
    }
    .modal-row {
        height: 50px;
        width: 100%;
    }
    .color {
        width: 40px;
        height: 40px;
        background: lightsalmon;
        margin: 3px;
    }
</style>


