<template>
  <div class="text-center">
    <v-menu
      v-model="menu"
      :close-on-content-click="false"
      :nudge-width="200"
      offset-x
    >
      <template v-slot:activator="{ on }">
        <v-icon v-on="on" class="icon mx-1" :style="{color: color}">mdi-palette-outline</v-icon>
      </template>

      <v-card>
        <v-color-picker v-model="color" input="#000000"></v-color-picker>
      </v-card>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "ColorPicker",
  data: () => ({
      fav: true,
      menu: false,
      message: false,
      hints: true,
      color: '#A8A8A4'
  }),
}
</script>

<style>
  .icon {
    transition: all .3s;
  }
  .icon:hover {
    cursor: pointer;
    transform: scale(1.1);
  }
</style>