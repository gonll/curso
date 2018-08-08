<template>
  <div >
    <h1>Register</h1>
    <input type="email" name="email" placeholder="e-mail" v-model="email">
    <input type="password" name="pass" placeholder="password" v-model="pass">
    <button @click="register">Registrar</button>

</div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  data () {
    return {
        email:'',
        pass:''
    }
  },
  watch:{
    email(value){
        //console.log(value)
    }
  },
  methods: {
    async register(){
        const response = await AuthenticationService.register({
            email: this.email,
            password: this.pass
        })
        console.log(response.data);
        
    }
  }
}
</script>
