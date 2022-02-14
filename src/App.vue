<script setup>
// This starter template is using Vue 3 <script setup> SFCs

import { ref, onMounted } from "vue";
import axios from "axios";

// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
const users = ref([]);
onMounted(() => {
    axios.get("/api/users").then((res) => {
        console.log(res);
        users.value = res.data;
    });
});
</script>

<template>
    <ul>
        <li v-for="item in users" :key="item.id">
            用户ID：{{ item.id }}，用户名：{{ item.name }}test
        </li>
    </ul>
</template>

<style>
</style>
