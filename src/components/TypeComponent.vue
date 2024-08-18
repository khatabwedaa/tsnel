<script setup>
import { ref, computed, onMounted } from 'vue';

const word = ref('press start button');
const countDown = ref(6);
const model = ref('');
const words = ref(['php', 'function', 'postman', 'variable', 'text', 'program', 'rust', 'writing', 'laravel', 'javascript', 'iphone', 'banana', 'world', 'cars', 'cats', 'code', 'games', 'faster', 'small', 'object']);
const countScore = ref(0);
const arr = ref(0);

const isGameOver = computed(() => countDown.value <= 0 || countScore.value >= 200);

const countDownTimer = () => {
    if (!isGameOver.value) {
        setTimeout(() => {
            countDown.value--;
            isTrue();
            countDownTimer();
        }, 1000);
    }
};

const isTrue = () => {
    if (word.value === model.value) {
        countDown.value = 6;
        model.value = '';
        arr.value++;
        word.value = words.value[arr.value];
        countScore.value += 10;
    }
};

const start = () => {
    model.value = '';
    arr.value = 0;
    word.value = words.value[arr.value];
    countScore.value = 0;
    countDown.value = 5;
    countDownTimer();
};


</script>
<template>
    <div>
        <h1 class="text-3xl font-semibold">How Fast You Are ?</h1>
        <div class="mt-6 text-2xl">Type this word : <span class="font-semibold text-blue-600">{{ word }}</span></div>
        <div class="mt-2 text-xl text-red-500" v-if="countDown == 0">Sorry! try again</div>
        <div class="flex justify-between">
            <div class="text-2xl">Time : <span class="font-semibold text-blue-600">{{ countDown }}</span></div>
            <div class="text-2xl">Score : <span class="font-semibold text-blue-600">{{ countScore }}</span></div>
        </div>
        <input v-model="model"
            class="block px-4 py-2 mt-6 w-full text-gray-700 bg-gray-300 rounded border border-gray-300 appearance-none focus:outline-none focus:shadow-outline"
            type="email">
        <button class="px-4 py-2 mt-6 w-full text-white uppercase bg-blue-600 rounded" @click="start">start</button>
        <div v-if="countScore == 150" class="flex overflow-hidden fixed inset-0 z-50 justify-center items-center w-full"
            style="background: rgba(0,0,0,.7);">
            <div
                class="overflow-y-auto z-50 mx-auto w-11/12 bg-white rounded border border-blue-600 shadow-lg modal-container md:max-w-md">
                <div class="px-6 py-4 text-left modal-content">
                    <div class="flex justify-between items-center pb-3">
                        <p class="text-2xl font-bold">Winner</p>
                    </div>
                    <div class="my-5">
                        <p>Winner winner chicken dinner</p>
                    </div>
                    <div class="flex justify-end pt-2">
                        <button @click="start"
                            class="px-4 py-2 text-white bg-blue-600 rounded-lg hover:bg-blue-500">Play Agin</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
