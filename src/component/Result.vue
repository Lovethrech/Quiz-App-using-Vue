
<script setup>
import { defineProps } from "vue";
import { RouterLink } from "vue-router";
const {
    numberOfCorrectAnswers,
    quizQuestionLength } = defineProps([
        'numberOfCorrectAnswers',
        'quizQuestionLength'
]);
</script>

<template>
    <div class="results">
        <i class='bx bxs-party bx-flip-vertical bx-tada' ></i>
        <h2>Your final result is</h2>
        <h1>
            {{ numberOfCorrectAnswers }}/{{ quizQuestionLength }}
        </h1>
    </div>
    <div class="home-btn"><RouterLink class="result-home-btn" to="/">Go back</RouterLink></div>
   
</template>

<style scoped>
.results{
    margin: 0 auto;
    padding: 40px 20px;
    width: 90%;
    height:500px;
    box-shadow: 1px 1px 10px hsla(0, 0%,0%,0.2);
    text-align:center;
    font-size:30px;
}

.results i{
    color:hsl(33, 100%, 88%);
    font-size:140px;
}
.home-btn{
    text-align:right;
}
.result-home-btn{
    text-decoration: none;
    border:2px solid hsl(33, 100%, 88%);
    background-color: hsl(33, 100%, 88%);
    color: hsl(0, 0%, 0%);
    padding:10px 20px;
    font-size:20px;
    font-weight:700;
}
</style>