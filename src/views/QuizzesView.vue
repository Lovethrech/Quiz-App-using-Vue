<script setup>
import q from "../data/quizzes.json"
import { ref, watch } from "vue"
import Card from "../component/Card.vue"

const quizzes = ref(q);
const search = ref("");

watch(search, () => {
    quizzes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})
</script>

<template>
    <div class="main-container">
        <header>
            <h1>Quizzes</h1>
            <input v-model.trim="search" type="text" placeholder="Search...">
        </header>

        <div class="options-container">
            <Card v-for="quiz in quizzes" :key="quiz.id" :quiz="quiz"/>
        </div>

    </div>
</template>

<style scoped>
    header{
        margin: 30px 0 10px 0;
        display:flex;
        align-items:center;
    }
    header h1{
        font-weight:bold;
        margin-right:13px;
    }
    header input{
        border:0;
        background-color: hsla(26, 15%, 30%, 0.1);
        padding:10px;
        border-radius:15px;
    }
    .options-container{
        display:flex;
        flex-wrap: wrap;
        margin-top: 40px;
    }

</style>