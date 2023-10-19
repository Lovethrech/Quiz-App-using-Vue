<script setup>
import { defineProps, defineEmits } from "vue";

const emit = defineEmits(["selectOption"]);
const { question } = defineProps(['question']);
const emitSelectedOption = (isCorrect) => {
    emit("selectOption", isCorrect)
};
</script>

<template>
    <div class="question-container">
        <div class="question">
            <h2>{{ question.text }}</h2>
        </div>
        <div class="options-container">
            <div
            v-for="option in question.options" 
            :key="option.id" 
            class="options"
            @click="emitSelectedOption(option.isCorrect)"
            >
                <p class="option-label">{{ option.label }}:</p>
                <div class="option-value">
                    <p>{{ option.text }}</p>
                </div>
            </div>
        </div>
    </div>

</template>

<style scoped>
h2{
    font-size:34px;
}
.question-container{
    margin: 0 auto;
    padding:20px;
    width: 90%;
    height:500px;
    box-shadow: 1px 1px 10px hsla(0, 0%,0%,0.2);
}
.options-container{
    margin-top:10px;
}
.options{
    font-size:30px;
    display: flex;
    flex-direction:row;
    margin: 10px 0;
    padding: auto 0;
}
.options:hover{
    cursor:pointer;
}
.option-label{
    background-color: hsl(33, 100%, 88%);
    padding: 10px 20px;
    width: 60px;
    height:100%;
}
.option-value{
    margin: auto 0;
    cursor:pointer;
    padding: 10px 0 10px 30px;

}
.option-value:hover{
    background-color: rgba(93, 93, 88, 0.299);
    width:100%;
}

</style>