<template>
  <v-container>
    <v-row>
      <v-col
        cols="6"
        class="d-flex justify-center mx-auto"
      >
        <h2>Form Pendaftaran</h2>
      </v-col>
    </v-row>
    <v-row>
        <v-col>
        <v-form v-model="valid">
            <v-container>
              <v-row>
                <v-col
                  cols="6"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="firstName"
                    :rules="nameRules"
                    :counter="15"
                    label="First name"
                    required
                  ></v-text-field>
                </v-col>
                <v-col
                  cols="6"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="lastName"
                    :rules="nameRules"
                    :counter="15"
                    label="Last name"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
              <v-row>
                <v-col
                  cols="6"
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
                <v-col
                  cols="6"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="username"
                    :rules="usernameRules"
                    label="Username"
                    required
                  ></v-text-field>
                </v-col>
              </v-row>
             <v-row>
                <v-col
                  cols="6"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="password"
                    :rules="passwordRules"
                    label="Password"
                    type="password"
                    required
                  ></v-text-field>
                </v-col>
                <v-col
                  cols="6"
                  md="4"
                  class="mx-auto"
                >
                  <v-text-field
                    v-model="confirmPassword"
                    :rules="confirmPasswordRules"
                    label="Confirm Password"
                    type="password"
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
          Daftar
        </v-btn>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        cols="12"
        md="4"
        class="d-flex justify-center mx-auto"
      >
        <a href="/login">sudah punya akun ? login sini ngab</a>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: false,
    firstName: '',
    lastName: '',
    username: '',
    email: '',
    password: '',
    confirmPassword: '',
    nameRules: [
      v => !!v || 'Name wajib diisi',
      v => v.length <= 15 || 'Name maksimal 15 karakter'
    ],
    emailRules : [
      v => !!v || 'Email wajib required',
      v => /.+@.+/.test(v) || 'E-mail tidak valid'
    ],
    usernameRules:  [
      v => !!v || 'Username wajib diisi',
      v => v.length <= 15 || 'Username must be less than 15 character'
    ],
    passwordRules: [
      v => !!v || 'Password wajib diisi',
      v => v.length >= 8 || 'Password minimal 8 karakter',
      v => v.length <= 15 || 'Password maksimal 8 karakter'
    ]
  }),
  computed: {
    confirmPasswordRules(){
      return [
        (v) => !!v || 'Confirm password wajib diisi',
        () => (this.password === this.confirmPassword) || 'Password tidak cocok'
      ]
    }
  }
}
</script>









