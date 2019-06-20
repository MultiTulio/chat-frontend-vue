<template>
  <div class='login'>
  <div class='username'>
        <span>Ваш логин:</span>
        <input v-model='userLogn' type = 'text' placeholder = 'Введите логин'/>
  </div>
  <div class='password'>
        <span>Ваш пароль:</span>
        <input v-model='userPswd' type = 'text' placeholder = 'Введите пароль'/>
  </div>
    <div class='input-wrap'>
        <button v-on:click = 'checkUser' name='submit'>Войти</button>
    </div>

  </div>
</template>

<script>
export default {
    data(){
      
    },
    methods: {
        checkUser() {
            
        }
    }
}
</script>

<style>

</style>
