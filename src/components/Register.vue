<template>


    <form @submit.prevent="handleSubmit">
        <h3 class="mb-4 pb-2 pb-md-0 mb-md-5">Регистрация</h3>
  <div class="mb-3">
    <label for="exampleInputEmail" class="form-label">Email</label>
    <input type="email" class="form-control" id="exampleInputEmail" v-model="exampleInputEmail" aria-describedby="emailHelp">
    
  </div>
  <div class="mb-3">
    <label for="exampleInputName" class="form-label">Имя</label>
    <input type="Name" class="form-control" id="exampleInputName" v-model="exampleInputName" aria-describedby="NameHelp">
    
  </div>
    <div class="mb-3">
        <label class="form-label" for="phoneNumber">Телефон</label>
        <input type="tel" id="phoneNumber" v-model="phoneNumber" class="form-control form-control-lg" />
        

    </div>
  <div class="mb-3">
    <label for="exampleInputPassword" class="form-label">Пароль</label>
    <input type="password" class="form-control" v-model="exampleInputPassword" id="exampleInputPassword">
  </div>

  
  <div class="mb-3">
    <label for="foryou" class="form-label">О себе</label>
    <input type="text" class="form-control" id="foryou" v-model="foryou" aria-describedby="NameHelp">
    
  </div>
  <button type="submit" class="btn btn-primary">Зарегистрироваться</button>
</form>
</template>


<script>
    
    import axios from "axios"
    export default {
        name:'Register',
        data(){
            return{
                exampleInputEmail: '',
                exampleInputName: '',
                phoneNumber: '',
                exampleInputPassword:'',
                foryou:''


            }
        },
        methods:{
          
          
          async handleSubmit(){
            
                    await axios.post(axios.defaults.baseURL,{
                    exampleInputEmail:this.exampleInputEmail,
                    exampleInputName:this.exampleInputName,
                    phoneNumber: this.phoneNumber,
                    exampleInputPassword: this.exampleInputPassword,
                    foryou: this.foryou
                });
                
                this.$router.push('/login')
            }
        }
      }
    
</script>



