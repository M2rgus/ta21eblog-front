<script setup>
import { ref } from 'vue';
import { useAuthStore } from '../stores/auth.js';
import { useRouter } from 'vue-router'



let email = ref('');
let password = ref('');
async function register(){
    await auth.register(email.value, password.value);
    router.push('/');
}
</script>
<template>
    <div class="container">
    <b-field label="Email">
            <b-input type="email" v-model="email"></b-input>
    </b-field>
    <b-field label="Password">
        <b-input type="password" v-model="password"></b-input>
    </b-field>
    <b-button @click="register">Register</b-button>
    </div>
</template>