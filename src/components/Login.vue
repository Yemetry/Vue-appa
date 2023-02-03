<template>
<h3 class="mb-4 pb-2 pb-md-0 mb-md-5">Вход</h3>
<form @submit.prevent = "handleSubmit">
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email</label>
    <input type="email" class="form-control" id="exampleInputEmail1" v-model="email" aria-describedby="emailHelp">
    
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Пароль</label>
    <input type="password" class="form-control" v-model="password" id="exampleInputPassword1">
  </div>
  <button type="submit" class="btn btn-primary">Авторизироваться</button>
</form>
</template>

<script>
import axios from "axios"
export default {
    name: 'Login',
    data(){
      return{
        email:'',
        password:''
      }

    },
    methods:{
      async handleSubmit(){
        const respounse = await axios.post('login',{
          email: this.email,
          password: this.password
        })
        localStorage.setItem('token',respounse.data.token);
        this.$router.push('/');
      }
    }
}
</script>