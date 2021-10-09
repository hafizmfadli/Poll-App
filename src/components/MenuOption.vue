<template>
  <v-container>
    <v-row>
      <v-img
        :src="require(`../assets/${imgName}`)"
        class="my-3"
        contain
        height="200"
      ></v-img>
    </v-row>
    <v-row>
      <v-col
        cols="12"
        class="d-flex justify-center mx-auto"
      >
        <v-btn
          color="primary"
        >
          {{ btnTitle }}
        </v-btn>
      </v-col>
    </v-row>
  </v-container>  
</template>

<script>
export default {
  data: () => ({

  }),
  props: {
    imgName: String,
    btnTitle: String
  }
}
</script>
