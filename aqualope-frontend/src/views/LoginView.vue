<template>
    <MenuHeader></MenuHeader>



<div class="card shadow-sm m-auto" style="max-width: 22vw;">
<main class="form-signin w-100 m-auto">
  <form @submit.prevent>
    <h1 class="h3 mb-3 fw-normal text-center">Sing In</h1>
    <span class="text-center" style="color: grey;">use your free-ipa account</span>
    <div class="form-floating">
      <input v-model="userLogin" type="text" class="form-control" id="floatingInput" placeholder="Login">
      <label for="floatingInput">Login</label>
    </div>
    <div class="form-floating">
      <input v-model="userPassword" type="password" class="form-control" id="floatingPassword" placeholder="Password">
      <label for="floatingPassword">Password</label>
    </div>
    <span v-html="errorInfo" class="auth-error"></span>
    <button class="btn btn-primary w-100 py-2" type="submit" @click="loginBtnFunc">Sign in</button>
  </form>
</main>
</div>   
</template>

<script>
import { defineComponent, ref } from 'vue';
import MenuHeader from '@/components/MenuHeader.vue'
import { useRouter } from 'vue-router';

export default defineComponent({
  name: 'LoginPage',
  components: {
    MenuHeader,
  },
  setup() {

    // Данные формы входа
    const userLogin = ref('');
    const userPassword = ref('');
    const errorInfo = ref('');

    // Метод для отправки данных входа

    return {
      userLogin,
      userPassword,
      errorInfo,
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-signin {
  max-width: 330px;
  padding: 1rem;
}

.form-signin .form-floating:focus-within {
  z-index: 2;
}

.form-signin input[type="email"] {
  margin-bottom: -1px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}

.form-signin input[type="password"] {
  margin-bottom: 10px;
  border-top-left-radius: 0;
  border-top-right-radius: 0;
}

.auth-error {
    color: #da1212;
}
</style>