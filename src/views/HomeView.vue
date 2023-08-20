<script setup>
import { ref } from 'vue';
import { useUserStore }  from '@/stores/user';

const userStore = useUserStore();
const email = ref("");
const password = ref("");

</script>

<template>
<h1>ToDo List</h1>
<h2 v-if="userStore.user">Current User: {{ userStore.user.user.email }}</h2>
<input placeholder="Write your email" v-model="email">
<input placeholder="Write your password" v-model="password">
<button @click="userStore.createNewUser(email, password)">Create New User</button>
</template>
