<script setup>
import { computed } from 'vue';

const props = defineProps ({
    temp: {
        type: Object,
        required: true 
    },
    get_data:{
        type: Function,
        required: true 
    },
    getFtemp: {
        type: Function,
        required: true 
    },
    isButtonOneActive: {
        type: Boolean,
        required: true 
    }
})

const showTemp = computed(()  => { return "Температура: " + props.temp.main.temp })
const showFeelsLike = computed(() => { return "Ощущается как: " + props.temp.main.feels_like })
const showMinTemp = computed(() => { return "Минимальная температура: " + props.temp.main.temp_min })
const showMaxTemp = computed(() => { return "Максимальная температура: " + props.temp.main.temp_max })

</script>

<template>
<div v-if = "props.temp" class = "infoTemp">
    <div class = "changeBtn"> 
        <button class = "btnTemp" @click = "getFtemp" v-if = "isButtonOneActive"> Перевести в °F </button> 
        <button class = "btnTemp" @click = "get_data" v-if = "!isButtonOneActive"> Перевести в °C </button>
        <router-link to = "/info"> 
        <button class = "btnTemp" > Дополнительная информация </button>
        </router-link>
    </div>

    <div> 
        <h2> {{ showTemp }}</h2>
        <h2> {{ showFeelsLike }}</h2>
        <h2> {{ showMinTemp }}</h2>
        <h2> {{ showMaxTemp }}</h2>
    </div>
</div>

    
</template>

<style scoped>
.infoTemp {
    grid-area: content1; 
    display: grid;
    box-shadow: 0px 2px 40px #00000014;
    align-content: center; 
    justify-content: center;
    font-weight: 700;
    border-radius: 10px;
    grid-row: span 2;
    padding: 30px;
    margin-left: 50px;
}

.btnTemp {
    border-radius: 10px;
    border: 2px solid #0d0b87;
    padding: 10px 15px;
    margin-left: 20px;
    cursor: pointer;
    background: #0d0b87;
    color: #fff;
    transform: none !important;
}

.changeBtn {
    position: absolute;
}
</style>
