<template>
    <q-page class="bg-grey-3">
      <div class="row">
        <q-card class="fixed-center col-md-4 col-xs-12 bg-white
        " flat>
          Login Page
        <q-form
        @submit="onSubmit"
        @reset="onReset"
        @register="onRegister"
        class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Insert your Username"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Insert your password"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
        <q-btn to="register" label="register" type="register" color="amber" />
      </div>
        </q-form>
        </q-card>
      </div>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'nopri' && this.password === '123') {
        this.$q.notify({
          type: 'positive',
          message: 'selamat berhasil login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'gagal login, username atau password anda salah'
        })
      }
    },
    onReset () {
      console.log('ini fungsi reset')
    },
    onRegister () {
      console.log('ini fungsi register')
    }
  }
}
</script>
