<template>
  <div >
   <h1>Register</h1>
   <input type="text" name="email" placeholder="email" v-model="email"/><br/>
   <input type="password" name="password" placeholder="password" v-model="password"/><br/>
   <button @click="handleRegister">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {

  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async handleRegister () {
      await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  },
  watch: {
    email (value) {
      console.log('email change', value)
    }
  },
  mounted () {
    // setTimeout(() => {
    //   this.email = 'Hellow World'
    // }, 2000)
  }
}
</script>
