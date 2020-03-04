<template>
    <div>
        <h1 class="text-3xl font-semibold">How Fast You Are ?</h1>
        <div class="text-2xl mt-6">Type this word : <span class="text-blue-600 font-semibold">{{ word }}</span></div>
        <div class="flex justify-between">
            <div class="text-2xl">Time : <span class="text-blue-600 font-semibold">{{ countDown }}</span></div>
            <div class="text-2xl">Score : <span class="text-blue-600 font-semibold">{{ countScore }}</span></div>
        </div>
        <input v-model="model" class="mt-6 bg-gray-300 text-gray-700 focus:outline-none focus:shadow-outline border border-gray-300 rounded py-2 px-4 block w-full appearance-none" type="email">
        <button class="w-full mt-6 px-4 py-2 bg-blue-600 text-white uppercase rounded" @click="start">start</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                word: 'press start button',
                countDown: 5,
                model: '',
                words: [ 'php' , 'john' , 'bostman' , 'steve' , 'text' , 'laracon' , 'laracast' , 'haha' , 'iphone' , 'banana' , 'world' , 'cars' , 'cats' , 'vscode' ],
                countScore: 0 ,
                arr: 0
            }
        },
        methods : {
            countDownTimer() {
                if(this.countDown > 0) {
                    setTimeout(() => {
                        this.countDown -= 1
                        this.isTrue()
                        this.countDownTimer()
                    }, 1000)
                }
            },
            isTrue() {
                if(this.word == this.model)
                {
                    this.countDown = 5
                    this.model = ''
                    this.word = this.words[this.arr]; this.arr++
                    this.countScore += 5
                }
            },
            start() {
                this.model = ""
                this.arr = 0
                this.word = this.words[this.arr]; this.arr++
                this.countScore = 0
                this.countDown = 5
                this.countDownTimer()
                this.isTrue()
            }
        },
    }
</script>