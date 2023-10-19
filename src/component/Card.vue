<script setup>
import { defineProps } from "vue"
import { useRouter } from "vue-router";

const router=useRouter()
const { quiz } = defineProps(['quiz'])

// An error function
const navigateToQuiz = () => {
    router.push(`/quiz/${quiz.id}`)
}
</script>

<template>
    <div class="card" @click="navigateToQuiz()">
        <div class="img"><img :src="quiz.img" alt=""></div>
        <div class="card-text">
            <h2>{{ quiz.name }}</h2>
            <p>{{ quiz.questions.length }} Questions</p>
        </div>
    </div>
</template>
<style scoped>
    .card{
        max-width: 310px;
        overflow: hidden;
        border-radius: 2%;
        box-sizing: 1px 1px 10px hsla(0, 10%, 8%, 0.979);
        margin:0 25px 30px 0;
        cursor: pointer;
    }
    .card .card-text{
        padding: 0 5px;
    }
    .card .card-text h2{
        font-weight:bold;
    }
    .card img{
        width:100%;
        height:230px;
    }
</style>