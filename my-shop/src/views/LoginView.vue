<script setup>
import {ref} from 'vue'
import axios from 'axios';

const email = ref('john@gmail.com')
const password = ref('123456')

const Login = async() =>{
    try{
    axios.post('http://127.0.0.1:8000/api/login',{
        email: email.value,
        password: password.value
    });
    // console.log("user Login successfully")
}
catch(error){
    // console.log("Error Login user")
    }
}
</script>

<template>
    <v-sheet class="mx-auto mt-5 pa-12" max-width="500"  elevation="12">
        <v-form>
            <v-text-field
            label="Enter email" variant="outlined" v-model="email">
            </v-text-field>
            <v-text-field
            label="Enter password" variant="outlined" v-model="password">
            </v-text-field>
            <v-btn density="comfortable" rounded="sm" elevation="4" color="green" @click="Login">Login</v-btn>
        </v-form>
    </v-sheet>
</template>