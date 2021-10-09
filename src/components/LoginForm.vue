<template>
  <v-container>
    <v-row>
      <v-col>
        <v-img
          :src="require('../assets/logo.png')"
          class="my-3"
          contain
          height="200"
        ></v-img>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-form v-model="valid">
            <v-container>
              <v-row>
                <v-col
                  cols="12"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="username"
                    :rules="usernameRules"
                    :counter="15"
                    label="Username"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-row>
                <v-col
                  cols="12"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
            </v-container>
        </v-form>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        cols="12"
        class="d-flex justify-center mx-auto"
      >
        <v-btn
          :disabled="!valid"
          color="primary"
        >
          Masuk
        </v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        cols="12"
        md="4"
        class="d-flex justify-center mx-auto"
      >
        <a href="/register">Belum punya akun ? daftar sini ngab</a>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      valid: false,
      username: '',
      usernameRules: [
        v => !!v || 'Username wajib diisi',
        v => v.length <= 15 || 'Username maksimal 15 karakter',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail wajib diisi',
        v => /.+@.+/.test(v) || 'E-mail tidak valid',
      ],
    }),
  }
</script>