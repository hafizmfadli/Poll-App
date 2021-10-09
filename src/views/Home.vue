<template>
  <v-container>
    <v-row>
      <v-col
        cols="12"
        md="6"
      >
        <menu-option btnTitle='Buat Poll' imgName='logo.svg' />
      </v-col>
      <v-col
        cols="12"
        md="6"
      >
       <menu-option btnTitle='Ikuti Poll' imgName='logo.png' />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  import MenuOption from '../components/MenuOption.vue'
  export default {
    name: 'Home',
    components: {
      MenuOption
    },
  }
</script>
