<template>
    <v-footer padless class="footer">
    <v-col class="text-center blue--text text--lighten-5" cols="12">
      {{ new Date().getFullYear() }} — <strong>Poster Generator</strong>
    </v-col>
  </v-footer>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .footer {
        background: #6B8798 !important;
    }
</style>