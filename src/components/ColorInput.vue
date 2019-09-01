<template>
  <div>
      <v-subheader class="pl-0 label">{{ label }}</v-subheader>
      <div class="d-flex justify-space-between">
        <div class="color-input d-flex align-center">
          <input type="text" v-model="color" v-on:input="$emit('colorValue', $event.target.value)">
          <ColorPicker @colorValue="emitColorValue" />
        </div>
        <input v-if="!url" type="file" class="file-input" id="file-input" @change="getFileURL">
        <label v-if="!url" for="file-input" class="file-button">Upload image</label>
        <v-btn v-if="url" outlined color="error" rounded class="delete-image" @click="deleteBackgroundImage">Delete image</v-btn>
      </div>
  </div>
</template>

<script>
    import ColorPicker from '../components/ColorPicker.vue'

    export default {
      name: 'ColorInput',
      props: ['label'],
      components: {
        ColorPicker
      },
      data: function() {
        return {
          color: "#A8A8A4",
          url: null
        }
      },
      methods: {
        emitColorValue(value) {
          this.color = value;
          this.$emit("colorValue", value);
        },
        getFileURL(file) {
          const img = file.target.files[0];
          const reader = new FileReader();


          reader.readAsDataURL(img);
          reader.onload = file => {
            this.url = file.target.result;
            console.log(file);

            this.$emit("imageValue", this.url);
          }
        },
        deleteBackgroundImage() {
          this.url = null;
          this.$emit("imageValue", this.url);
        }
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
    height: 36px;
  }
  .file-input {
    width: 0.1px;
    height: 0.1px;
    opacity: 0;
    overflow: hidden;
    position: absolute;
    z-index: -1;
  }
  .file-button {
    border: 1px solid #1867c0;
    color: #1867c0;
    border-radius: 28px;
    font-size: 13px;
    width: 100%;
    height: 36px;
    margin-left: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-transform: uppercase;
    font-weight: 500;
    letter-spacing: .5px;
    transition: all .3s;
  }
  .file-button:hover {
    cursor: pointer;
    background: #fafcff;
  }
  .delete-image {
    font-size: 13px;
    letter-spacing: .5px;
    width: 151px;
  }
  /* .file-input:focus + label {
    outline: 1px dotted #000;
	  outline: -webkit-focus-ring-color auto 5px;
  } */
</style>