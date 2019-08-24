<template>
    <div>
        <d-puzzle v-bind="puzzleConfig[level]" @next="handleNext" />
    </div>

    
</template>

<script>
import DPuzzle from './Puzzle';

export default {
    components:{
        DPuzzle
    },
    data() {
        return {
            level:0,
            puzzleConfig:[
                {row: 3, col: 3, img:'./puzzleImg/cat1.jpg'},
                {row: 4, col: 4, img:'./puzzleImg/cat2.jpg'},
                {row: 5, col: 5, img:'./puzzleImg/cat3.jpg'},
                {row: 6, col: 6, img:'./puzzleImg/cat4.jpg'},
                {row: 8, col: 8, img:'./puzzleImg/cat5.jpg'},
            ]
        }
    },
    methods: {
        handleNext(){
            if(++this.level == this.puzzleConfig.length){
                const answerFlag = window.confirm('你已通关，要重来吗？');
                if(answerFlag){
                    this.length = 0;
                }
            }
            console.log('next');
        }
        
    },
}
</script>