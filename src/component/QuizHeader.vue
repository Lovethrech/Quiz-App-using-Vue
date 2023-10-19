<script setup> 
import { defineProps } from "vue";

const { questionStatus, barPercentage } = defineProps(['questionStatus', 'barPercentage']);

</script>

<template>
    <header>
        <h4>Question {{ questionStatus }}</h4>
        <div class="bar">
            <div class="completion" :style="{width:barPercentage}"></div>
        </div>
    </header>
</template>

<style scoped>
header{
    margin:20px 10px;
}
h4{
    font-weight: 800px;
    font-size: 30px;
    text-align:center;
}
.bar{
    margin: 10px auto;
    width: 300px;
    height: 50px;
    border: 2px solid hsl(33, 100%, 88%);
}
.completion{
    height:100%;
    background-color: hsl(33, 100%, 88%);
}
</style>