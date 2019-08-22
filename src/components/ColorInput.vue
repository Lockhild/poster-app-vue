<template>
  <div>
      <v-subheader class="pl-0 label">Poster background</v-subheader>
      <div class="d-flex justify-space-between">
        <div class="color-input d-flex align-center">
          <input type="text">
          <ColorPicker />
        </div>
        <v-btn 
          outlined 
          rounded
          color="primary">Upload image</v-btn>
      </div>
  </div>
</template>

<script>
    import ColorPicker from '../components/ColorPicker.vue'

    export default {
      name: 'ColorInput',
      components: {
        ColorPicker
      }
    }
</script>

<style>
  .color-input {
    border: 1px solid #c2c2c2;
    border-radius: 5px;
  }
  .color-input > input {
    outline: none;
    padding: 0 8px;
    max-width: 165px;
  }
</style>