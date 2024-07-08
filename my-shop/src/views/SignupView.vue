<script setup>
import {ref} from 'vue'

const username = ref('john')
const email = ref('john@gmail.com')
const password = ref('123456')

function signup(){
    console.log(`${username.value} ${email.value} ${password.value} `)
}
</script>

<template>
    <v-sheet class="mx-auto mt-5 pa-12" max-width="500"  elevation="12">
        <v-form>
            <v-text-field
            label="Enter username" variant="outlined" v-model="username">
            </v-text-field>
            <v-text-field
            label="Enter email" variant="outlined" v-model="email">
            </v-text-field>
            <v-text-field
            label="Enter password" variant="outlined" v-model="password">
            </v-text-field>
            <v-btn density="comfortable" rounded="sm" elevation="4" color="green" @click="signup">Signup</v-btn>
        </v-form>
    </v-sheet>
</template>