<template>

    <q-page
      >
      <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="nama"
        label="Insert your name "
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

      <q-input
        filled
        v-model="username"
        label="Insert your Username"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

       <div class="q-pa-md">
         Kelamin anda: <strong>{{ gender }}</strong>
    <div class="q-gutter-sm">
      <q-radio v-model="gender" val="Laki-laki" label="Laki-laki" />
      <q-radio v-model="gender" val="Perempuan" label="Perempuan" />
    </div>
    <div class="q-px-sm">
    </div>
  </div>

      <q-input
        filled
        type="password"
        v-model="password"
        label="Insert your Password"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

      <q-input
        filled
        type="password"
        v-model="repassword"
        label="Retype your password"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

      <q-input
        filled
        v-model="email"
        label="Insert your E-Mail"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Ketik lhaa jangan mager']"
      />

      <div>
        <q-btn to="/" label="Submit" type="submit" color="primary"/>
        <q-btn to="register" label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      nama: null,
      password: null,
      repassword: null,
      username: null,
      email: null,
      gender: null
    }
  },
  methods: {
    onSubmit () {
      console.log('ini fungsi submit')
    },
    onReset () {
      console.log('ini fungsi reset')
    }
  }
}
</script>
